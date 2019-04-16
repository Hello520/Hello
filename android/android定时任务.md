### android定时任务
	
1. 实现方式
	
	1.handler+runnable

	2.handler+timer+timertask

	    public class MainActivity extends Activity {
    	private TextView mytext1;
    	private TextView mytext2;
    	
    	private Handler MyHandler;
    	private Runnable MyTask;
    	
    	private Handler myHandler2;
    	private Timer myTimer;
    	private TimerTask myTask2;
    	private int MyCount = 0;
    	private int MyCount1 = 0;
    	@Override
    	protected void onCreate(Bundle savedInstanceState) {
    		super.onCreate(savedInstanceState);
    		setContentView(R.layout.activity_main);
    		
    		//初始化两个textview
    		initView();
    		//初始化data
    		initData();
    		MyHandler.postDelayed(MyTask, 1000);
    		myTimer.schedule(myTask2, 1000,1000);
    		
    		
    	}
    
    	private void initData() {
    		MyHandler = new Handler();
    		MyTask = new Runnable() {
    			
    			@Override
    			public void run() {
    				//todo想做的事
    				doWork();
    				if (MyHandler != null && MyCount < 10) {
    					MyHandler.postDelayed(this, 1000);	
    				}else {
    					MyHandler.removeCallbacks(MyTask); 
    				}
    			}
    		};
    		//第二种方法
    		myTimer = new Timer();
    		myHandler2 = new Handler(){
    			public void handleMessage(android.os.Message msg) {
    				//todo要做的事
    				if (msg.what == 1) {
    					doWork1();
    				}
    				if (msg.what == 2) {
    					stopTimer();
    				}
    				super.handleMessage(msg);
    			};
    		};
    		myTask2 = new TimerTask() {
    			
    			@Override
    			public void run() {
    				Message msg = new Message();
    				msg.what = 1;
    				myHandler2.sendMessage(msg);
    				if (MyCount1 >8) {
    					Message msg2 = new Message();
    					msg2.what = 2;
    					myHandler2.sendMessage(msg2);
    				}
    				
    			}
    		};
    		
    		
    	}
    
    	protected void stopTimer() {
    		myTimer.cancel();
    		
    	}
    
    	protected void doWork1() {
    		mytext2.setText(++MyCount1+"");
    		
    	}
    
    	protected void doWork() {
    		mytext1.setText(++MyCount+"");
    	}
    
    	private void initView() {
    		mytext1 = (TextView) findViewById(R.id.id_text1);
    		mytext2 = (TextView) findViewById(R.id.id_text2);
    	}
    }
    