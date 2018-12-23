   //创建定时器

    public class TimerTest02 {
    	public static void main(String[] args) {
    	//创建定时器
    	TimerTask runnable = new TimerTask() {
    	@Override
    	public void run() {
    		System.out.println("hello alibaba qa !!");
    	}
    };
    	Timer timer = new Timer();
    	long delay = 0;
    	long intevalPeriod = 1 * 1000;
    	timer.scheduleAtFixedRate(runnable, delay, intevalPeriod);
    	}
    }