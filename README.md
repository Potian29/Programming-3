using System;
namespace Timekeeping {
    class Program
{
    static void Main(string[]args) {

Console.WriteLine("Employee's Daily Time Record");
Console.WriteLine($"Today's Date: {DateTime.Today.ToShortDateString()}");

Console.WriteLine("________________________________");
Console.Write("To record your time-in please enter your Employee ID:");
string employeeId = Console.ReadLine();

TimeSpan timeIn = new TimeSpan(7,59,0);

Console.WriteLine($"Your login time has been recorded: {timeIn}");
Console.WriteLine("________________________________");
Console.Write("To record your time-out please enter your Employee ID:"); employeeId = Console.ReadLine();
TimeSpan timeOut = new TimeSpan(16, 00, 0);
Console.WriteLine($"Your logout time has been recorded: {timeOut}");
TimeSpan lunchBreakDuration = new TimeSpan(1, 0, 0);

TimeSpan totalHours = (timeOut - timeIn) - lunchBreakDuration;
Console.WriteLine($"Your total hours worked is: {totalHours}");
TimeSpan regularHoursStart = new TimeSpan(8, 0, 0);

TimeSpan regularHoursEnd = new TimeSpan(17, 0, 0);
TimeSpan lateIn = new TimeSpan(0,0,0);
TimeSpan earlyOut = new TimeSpan(0,0,0);

if (timeIn > regularHoursStart)
{
  lateIn = timeIn - regularHoursStart;}
   if (timeOut < regularHoursEnd)
{
  earlyOut = timeOut - regularHoursEnd;
}

TimeSpan totalUndertimeHours = regularHoursEnd - timeOut;
Console.WriteLine($"Your total Undertime hour/s is: {totalUndertimeHours}"); 

  }
 } 
}
