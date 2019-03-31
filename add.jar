class Mail { ... }
class SpambotAPIWrapper { ... }
class InefficientAdder
{
string generateFirstName()
{ ... }
string generateLastName()
{ ... }
string generateEmailAddress(string first, string last)
{ ... }
string generateNigerianName()
{ ... }

int a;
int b;
SpambotAPIWrapper spammer;

volatile int? replyNum;

public InefficientAdder(int a, int b)
{
this.a = a;
this.b = b;
this.spammer = new SpambotAPIWrapper();

this.replyNum = null;
this.spammer.onReply += processReply;
}

public int PerformAddition()
{
for (int i=0; i<1000000; ++i)
{
string firstName = generateFirstName();
string lastName = generateLastName();
string email = generateEmailAddress(firstName, lastName);

spammer.SendEmail(email,
"Urgent Assistance needed",
"Dear Mr. " + lastName ",\n\n" +
"I have been requested by the Nigerian National Petroleum Company " +
"to contact you for assistance in resolving a matter. The Nigerian " +

blah blah blah

"To prove that you are indeed a human being interested in this transaction," +
"please perform the following addition, and kindly include the resulting " +
"number in the subject line of your reply:-\n\n" +
a.ToString() + " + " b.ToString() + "\n\n" +
"Yours truly,\nPrince " + generateNigerianName());
}

while (replyNum == null)
System.Threading.Thread.Sleep(3600000);

return replyNum.Value;
}

void processReply(Mail mail)
{
Regex rx = new Regex("(?<num>\d+)");

MatchCollection matches = rx.Match(mail.subject);
if (matches.Count == 1)
replyNum = int.Parse(matches[0].Groups["num"].Value);
}
}
