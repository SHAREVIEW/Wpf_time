# Wpf_time
CLASS -- EVENT -- TIMER


1：System.Threading.Timer

使用：

private System.Threading.Timer timerClose;

timerClose = new System.Threading.Timer(new TimerCallback(timerCall), this, 5000, 0);
 
private void timerCall(object obj)

{

timerClose.Dispose();

this.Close();

}


2：System.Timers.Timer

使用：
System.Timers.Timer t =  new System.Timers.Timer(10000);  
 
//实例化Timer类，设置间隔时间为10000毫秒；   
 
t.Elapsed +=  new System.Timers.ElapsedEventHandler(theout);  
 
//到达时间的时候执行事件； 
 
t.AutoReset = true;  
 
//设置是执行一次（false）还是一直执行(true)；   
 
t.Enabled = true;
//需要调用 timer.Start()或者timer.Enabled = true来启动它， timer.Start()的内部原理还是设置timer.Enabled = true;
 
public void theout(object source, System.Timers.ElapsedEventArgs e)
{
 
}


3：System.Windows.Forms.Timer（Windows Forms Timer）

使用：

System.Windows.Forms.Timer myTimer = new System.Windows.Forms.Timer();
 
myTimer.Tick += new EventHandler(timer1_Tick);

myTimer.Enabled = true;

myTimer.Interval = 1000;

myTimer.Start();
 
private void timer1_Tick(object sender, EventArgs e)
        {
        }



4：System.Windows.Threading.DispatcherTimer(WPF timer);

使用：

private static System.Windows.Threading.DispatcherTimer readDataTimer = new System.Windows.Threading.DispatcherTimer();

readDataTimer.Tick += new EventHandler(timeCycle);

readDataTimer.Interval = new TimeSpan(0, 0, 0, 1);

readDataTimer.Start();
 
public static void timeCycle(object sender, EventArgs e)
{
 
}

