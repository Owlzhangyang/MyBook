###JavaExercise


***

1. 为考试成绩划定五个级别，当成绩大于或等于90分时，划定为优；当成绩大于或等于80且小于90时，划定为良；当成绩大于或等于70且小于80时，划定为中；当成绩大于或等于60且小于70时，划定为及格；当成绩小于60时，划定为差.使用if语句.
		public class Text01 {

		public static void main(String[] args) {
		String input = JOptionPane.showInputDialog("请输入成绩：");
		int score = Integer.parseInt(input);
		if(score>100){
		System.out.println("输入成绩错误，请填写0-100内正确成绩！");
		}else if (score>=90){
			System.out.println("优");
		}else if(score>=80){
			System.out.println("良");
		}else if(score>=70){
			System.out.println("中");
		}else if(score>=60){
			System.out.println("及格");
		}else if(score<60){
			System.out.println("不及格");
		}
		}
		}
		
2. 使用switch结构重写上面代码
		public class Text02 {

		public static void main(String[] args) {
		String input = JOptionPane.showInputDialog("请输入成绩：");
		int score = Integer.parseInt(input);
		if(score>100){
			JOptionPane.showMessageDialog(null, "请输入正确的成绩");
			return;
		}
		switch(score/10){
		case 10:
			JOptionPane.showMessageDialog(null, "优秀");
			break;
		case 9:
			JOptionPane.showMessageDialog(null, "优秀");
			break;
		case 8:
			JOptionPane.showMessageDialog(null, "良");
			break;
		case 7:
			JOptionPane.showMessageDialog(null, "中");
			break;
		case 6:
			JOptionPane.showMessageDialog(null, "及格");
			break;
		default:
			JOptionPane.showMessageDialog(null, "不合格");
		}
		System.exit(0);

		}

		}
		
3. 给出年份、月份，计算输出该月的天数 使用switch
		public class Text03 {

		public static void main(String[] args) {
		String sYear=JOptionPane.showInputDialog(null,"请输入年份:","年份输入",JOptionPane.DEFAULT_OPTION);
		if(sYear.equals("")){
			JOptionPane.showMessageDialog(null, "年份不能为空");
			System.exit(0);
		}
		int year = Integer.valueOf(sYear).intValue();
		if(year<0){
			JOptionPane.showMessageDialog(null, "年份不能为负数");
			System.exit(0);
		}
		
		String sDay=JOptionPane.showInputDialog(null,"请输入月份:","月份输入",JOptionPane.DEFAULT_OPTION);
		if(sDay.equals("")){
			JOptionPane.showMessageDialog(null, "月份不能为空");
			System.exit(0);
		}
		int day = Integer.parseInt(sDay);
		if(day>12){
			JOptionPane.showMessageDialog(null, "输入月份错误，请重新输入");
			System.exit(0);
		}
		switch(day){
		case 1:
		case 3:
		case 5:
		case 7:
		case 8:
		case 10:
		case 12:
			JOptionPane.showMessageDialog(null, "31天");
			break;
		case 2:{
			if((year % 4 == 0 && year % 100 != 0) || year % 400 == 0){
				JOptionPane.showMessageDialog(null, "29天");
			}else {
				JOptionPane.showMessageDialog(null, "28天");
			}
		}
			break;
		default:
			JOptionPane.showMessageDialog(null, "30天");
			break;
		}
			}		   
		}
		
4. 计算sum=1+2+3+4+5+…+100 使用for循环
		public class TestFor {

		public static void main(String[] args) {
		int sum = 0;
		for(int i = 1;i<=100;i++){
			sum=sum+i;
		}
		System.out.println("sum="+sum);
		}
		}
		
5. 这是一个古典数学问题：一对兔子从它出生后第3个月起，每个月都生一对小兔子，小兔子3个月后又生一对小兔子，假设兔子都不死，求每个月的兔子对数。该数列为：1   1   2   3  5   8   13   21…  即从第3项开始，其该项是前两项之和。求100以内的波那契数列 分别使用for与while循环
		public class Text08 {

		public static void main(String[] args) {
		int a,b,c,d;
		a=1;
		b=1;
		System.out.print(a+" "+b +" ");
		while(a<100){
			c=a+b;
			d=b+c;
			a=c;
			b=d;
			System.out.print(a+" "+b +" ");
		}
		}
		}
		
6. 计算n!, 当n=9时。并分别输出1！~9！各阶乘的值 使用while循环
		public class Text03 {

		public static void main(String[] args) {
		  int sum=1;
		  int i=1;
		  while(i<10){
			  sum*=i;
			  i++;
			  System.out.println(i-1+"的阶乘"+sum);
		  }		   
		  }
		}
		
7. 输出50~100以内的所有素数。所谓素数即是只能被1和其自身除尽的正整数。
		public class Text04 {

		public static void main(String[] args) {
		int n;
		boolean a = true;
		for (n = 50; n <= 100; n++) {
			a=true;
			for (int i = 2; i < n; i++) {
				if (n % i == 0) {
					a = false;
					break;
				}
			}
			if (a == true) {
				System.out.println(n+"是素数");
			} 
		}
		}

		}
		
8. 输出10~1000之间既能被3整除也能被7整除的数
		public class Text05 {

		public static void main(String[] args) {
		for (int n = 10; n <= 1000; n++) {
			if( (n%3==0)&&(n%7==0)){
				System.out.println(n);
			}
			}
		}
		}
		
9. 判断一个正整数是否是素数，若是计算其阶乘。判断素数和阶乘作为方法定义，并在主方法中调用它们
		public class Text07 {

		public static void main(String[] args) {
		String sA=JOptionPane.showInputDialog(null,"请输入数字:","数字输入",JOptionPane.DEFAULT_OPTION);
		int a =Integer.parseInt(sA);
		if(panduan(a)==true){
		System.out.println(a+"是素数,"+a+"的阶乘为:"+jiecheng(a));
		}else{
			System.out.println(a+"不是素数");
		}
		} 
		public static int jiecheng(int a){
		int c=1;
		int sum=0;
		for(c=1;c<a;c++){
			sum=a*c+a;
		}
		return sum;
		}
		public static boolean panduan(int a){
		for(int i=2;i<a;i++){
			if(a%i==0){
				return false;
			}
		}
		return true;
		}
		}
		




