# Lab Report 5

I found lab report 3 to be the most fun because I was able to experiment with new ways to use the command.

##Four Command Line Arguments for Grep

### -c

**Example 1**

```
grep -c "the" written_2/non-fiction/OUP/Castro/ChM.txt
```

**Output:**

```
65
```

The command -c returns the amount of times the file uses the word given. 
In this case, since "the" is a common word to use in english, it returns a high number of 65.

**Example 2**

```
grep -c "Machismo" written_2/non-fiction/OUP/Castro/ChM.txt
```

**Output:**

```
3
```

In this example I chose to test on the same file but with a different word, instead of "the" I used "Machismo". 
I chose a less common word that would pop up in the file and using the command, I was able to find that it only appeared 3 times.

### -n

**Example 1**

```
grep -n "monarchy" written_2/travel_guides/berlitz1/HistoryFrance.txt 
```

**Output**

```
127:        post-Revolutionary France called the Ancien Régime. The monarchy made
196:        power and smoothed the path to an increasingly absolutist monarchy.
200:        crushed, saw the monarchy stronger than ever.
244:        monarchy gradually weakened.
267:        a constitutional monarchy similar to England’s, not a republic. Even
329:        At the end of the Napoleonic era, the monarchy was
331:        restored monarchy with the reforms of the Revolution and Napoleon’s
343:        the “bourgeois monarchy” of Louis-Philippe.
```
The command -n is similar to grep where it returns the lines where it contains the searched word.
But it also adds the line number of the sentence where the word appears.
In this example I chose "monarchy" in the HistoryFrance.txt and it appeared 8 times spaced apart from 
line 127 to line 343.

**Example 2**

```
grep -n "culture" written_2/travel_guides/berlitz1/IntroJapan.txt
```

**Output:**

```
27:        cultures and beliefs: the rice farmers in rural heartlands and the
136:        integral aspect of Japanese culture and lifestyle. Onsen range from
```

In this example I chose to try another text file and a different word to test grep -n.
In this one I tried the word "culture" in the IntroJapan file and it only appeared twice.
This command is useful because in the file it talks about multiple topics, like history and its geography,
so if I wanted to learn more about their culture I can go to these command lines instead.

### -C(NumberOfLines(n))

**Example 1**

```
grep -C1 "China"  written_2/travel_guides/berlitz1/IntroHongKong.txt
```

**Output:**

```
        reverted to Chinese sovereignty as a Special Administrative Region of
        the People’s Republic of China. Today Hong Kong remains a capitalist
        enclave with its laws and rights intact, and China has promised that
        Hong Kong will continue in this fashion for at least 50 years.
        Beijing’s announced policy of maintaining Hong Kong’s prosperity and
        stability makes sense. Hong Kong has long been China’s handiest window
        on the West, and the city is unrivaled in its commercial know-how and
--
        Elizabeth has vanished from the coinage, and the Union Jack has been
        replaced by the flag of China and the new Hong Kong flag with its
        bauhinia flower. But in fact, there have been changes, many of them due
--
        Of Hong Kong’s population, 98 percent are Chinese. The
        majority are Cantonese, born in Hong Kong, or from South China, but
        there are immigrants from all over China. The Chinese people have been
        described as hardworking and pragmatic, attitudes that have contributed
```
The command -C(N) returns the n number of lines before and after the searched word is found in the file.
It also has similar commands like -A(N) and -B(N) but instead of before AND after it is only before(B) or after(A).
In this example, "China" was mentioned several times so in order to seperate the outputs they used -- to indicate it.


**Example 2**

```
grep -C2 "destinations" written_2/travel_guides/berlitz1/IntroLasVegas.txt
```

**Output:**

```
        Middle America, Las Vegas is again on the verge of its next phase — top
        notch resort city. Today’s Las Vegas reigns as one of the world’s most
        popular travel and vacation destinations. World class accommodations,
        five-star dining, and shopping opportunities that rival every major
        city have added immeasurably to the city’s reputation for all-night
```

In this example, I searched the word "destinations" and it only came up one time.
This is useful because in regular grep it only shows the line it has the word which may not make sense,
so this gives good context to how the word "destinations" is used in the file.

### -v

**Example 1**

```
grep -v "a" written_2/non-fiction/OUP/Abernathy/ch6.txt
```

**Output:**

```
Setting Inventory Levels in the Store
Co = cost of oversupply
Cu = cost of under-supply
Periodic Versus Continuous Review

```

The command -v returns the lines that don't contain the searched word.
In this example I chose one of the most common words in english to see if any output would be
shown and the only part in the file that didn't contain "a" was when it explained what co and cu meant.

**Example 2**

```
grep -v "0" written_2/travel_guides/berlitz1/HandRHongKong.txt
```
**Output:**

```
        Recommended Hotels
        Hong Kong has some of the most luxurious hotels in the
        world, with representatives from all the major international chains.
        Hotels listed below have full air-conditioning, offer 24-hour or
        limited room service, and a wide range of facilities. Hong Kong hotels
        have excellent business services and conference facilities; many have
        shopping malls.
        Reservations are strongly recommended, particularly in
        summer and at Christmas. If you do arrive without making advance
        arrangements, the Hong Kong Hotel Reservation Center at the
        International Airport will be happy to arrange accommodations for you
        on your arrival.
        As a basic guide, the symbols below have been used to
        indicate high-season rates in Hong Kong dollars, based on double
        occupancy, with bath or shower. Unless otherwise noted, hotels take all
        added to the bill.
```

In this example I searched for a number instead of a word and it still worked. 
For this file, the number was the cost for the recommended hotels that was mentioned in the file.
This command is useful in case you don't care about the price, and just want to know the service provided.

### Sources used

https://www.geeksforgeeks.org/grep-command-in-unixlinux/


