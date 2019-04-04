# EP 2 Tests

Hierbei handelt es sich um eine automatisierte TestSuite um EP2 Aufgaben schnell
und einfach auf Fehler überprüfen zu können. Außerdem finden sich in diesem
Dokument auch alle Testcases um manuell einzelne Aufgaben testen zu können.

## Manuelle TestCases

### Class Participation

#### Getters

```
String racer = "Mikaela Shiffrin";
String race = "Lienz 2011 Ladies' Slalom";
int bibnumber = 40;
Participation testParticipation = new Participation(race, racer, bibnumber);

System.out.println(testParticipation.getRacer());
System.out.println(testParticipation.getRace());
System.out.println(testParticipation.getBibnumber());
```

Erwarteter Ouptut:

```
Mikaela Shiffrin
Lienz 2011 Ladies' Slalom
40
```

#### Extended Getters (AD-Hoc)

```
String racer = "Mikaela Shiffrin";
String race = "Lienz 2011 Ladies' Slalom";
int bibnumber = 40;
int place = 3;
String runtime = "IncredibleTime";
Participation testParticipation = new Participation(race, racer, bibnumber, place, runtime);

System.out.println(testParticipation.getRacer());
System.out.println(testParticipation.getRace());
System.out.println(testParticipation.getBibnumber());
System.out.println(testParticipation.getPlace());
System.out.println(testParticipation.getRuntime());
```

Erwarteter Output:

```
Mikaela Shiffrin
Lienz 2011 Ladies' Slalom
40
3
IncredibleTime
```

#### Print

```
String racer = "Mikaela Shiffrin";
String race = "Lienz 2011 Ladies' Slalom";
int bibnumber = 40;
Participation testParticipation = new Participation(race, racer, bibnumber);

testParticipation.print();
```

Erwarteter Output:

```
40 Mikaela Shiffrin (Lienz 2011 Ladies\' Slalom)
```

#### Print1 (AD-Hoc)

```
String racer = "Mikaela Shiffrin";
String race = "Lienz 2011 Ladies' Slalom";
int bibnumber = 40;
int place = 3;
String runtime = "IncredibleTime";
Participation testParticipation = new Participation(race, racer, bibnumber);
Participation testParticipation2 = new Participation(race, racer, bibnumber, place, runtime);

testParticipation.print();
testParticipation2.print1();
```

Erwarteter Output:

```
40 Mikaela Shiffrin (Lienz 2011 Ladies\' Slalom)
40 Mikaela Shiffrin (Lienz 2011 Ladies' Slalom); 3; IncredibleTime
```

### Class Startlist

#### Print

```
Startlist startlist = new Startlist(100);

startlist.add(new Participation("Kitzbühel", "Marcel Hirscher", 1));
startlist.add(new Participation("Kitzbühel", "Hermann Maier", 2));
startlist.add(new Participation("Kitzbühel", "Benni Raich", 3));

startlist.print();
```

Erwarteter Output:

```
1 Marcel Hirscher (Kitzbühel)
2 Hermann Maier (Kitzbühel)
3 Benni Raich (Kitzbühel)
```

#### PrintOrdered

```
Startlist startlist = new Startlist(100);

startlist.add(new Participation("Kitzbühel", "Benni Raich", 3));
startlist.add(new Participation("Kitzbühel", "Marcel Hirscher", 1));
startlist.add(new Participation("Kitzbühel", "Hermann Maier", 2));

startlist.printOrdered();
```

Erwarteter Output:

```
1 Marcel Hirscher (Kitzbühel)
2 Hermann Maier (Kitzbühel)
3 Benni Raich (Kitzbühel)
```

#### PrintPermutations

```
Startlist startlist = new Startlist(100);

startlist.add(new Participation("Kitzbühel", "Marcel Hirscher", 1));
startlist.add(new Participation("Kitzbühel", "Hermann Maier", 2));
startlist.add(new Participation("Kitzbühel", "Benni Raich", 3));

startlist.printPermutations();
```

Erwarteter Output:

```
1 Marcel Hirscher (Kitzbühel)
2 Hermann Maier (Kitzbühel)
3 Benni Raich (Kitzbühel)

1 Marcel Hirscher (Kitzbühel)
3 Benni Raich (Kitzbühel)
2 Hermann Maier (Kitzbühel)

2 Hermann Maier (Kitzbühel)
1 Marcel Hirscher (Kitzbühel)
3 Benni Raich (Kitzbühel)

2 Hermann Maier (Kitzbühel)
3 Benni Raich (Kitzbühel)
1 Marcel Hirscher (Kitzbühel)

3 Benni Raich (Kitzbühel)
1 Marcel Hirscher (Kitzbühel)
2 Hermann Maier (Kitzbühel)

3 Benni Raich (Kitzbühel)
2 Hermann Maier (Kitzbühel)
1 Marcel Hirscher (Kitzbühel)
```

### Class Parse

#### ParseRec

```
System.out.println(Parse.parseRec(""));
System.out.println(Parse.parseRec("()<>"));
System.out.println(Parse.parseRec("(([(<>)])){()}<{}>"));
System.out.println(Parse.parseRec("("));
System.out.println(Parse.parseRec(")"));
System.out.println(Parse.parseRec("(a)"));
System.out.println(Parse.parseRec("(]")));
```

Erwarteter Output:

```
true
true
true
false
false
false
false
```

#### ParseStack

```
System.out.println(Parse.parseStack(""));
System.out.println(Parse.parseStack("()<>"));
System.out.println(Parse.parseStack("(([(<>)])){()}<{}>"));
System.out.println(Parse.parseStack("("));
System.out.println(Parse.parseStack(")"));
System.out.println(Parse.parseStack("(a)"));
System.out.println(Parse.parseStack("(]")));
```

Erwarteter Output:

```
true
true
true
false
false
false
false
```

#### ParseStack1

```
System.out.println(Parse.parseStack1(""));
System.out.println(Parse.parseStack1("()<>"));
System.out.println(Parse.parseStack1("(([(<>)])){()}<{}>"));
System.out.println(Parse.parseStack1("("));
System.out.println(Parse.parseStack1(")"));
System.out.println(Parse.parseStack1("(a)"));
System.out.println(Parse.parseStack1("(]")));
```

Erwarteter Output:

```
true
true
true
false
false
false
false
```

### Class CharStack

#### Pop

```
CharStack cs = new CharStack();

cs.push('y');
cs.push('e');
cs.push('h');


System.out.println(cs.pop());
System.out.println(cs.pop());
System.out.println(cs.pop());
System.out.println(cs.pop());
```

Erwarteter Output:

```
h
e
y

```

#### Push

```
CharStack cs1 = new CharStack();
CharStack cs2 = new CharStack();
CharStack cs3 = new CharStack();

cs2.push('y');
cs2.push('e');
cs2.push('h');
cs2.pop();

cs3.push('y');
cs3.push('e');
cs3.push('h');
cs3.pop();
cs3.pop();
cs3.pop();
cs3.pop();
cs3.pop();
cs3.pop();

System.out.println(cs1.isEmpty());
System.out.println(cs2.isEmpty());
System.out.println(cs3.isEmpty());
```

Erwarteter Output:

```
true
false
true
```

### Class Participations

#### Print

```
Participations participations = new Participations(100);

participations.add(new Participation("Kitzbühel", "Marcel Hirscher", 1));
participations.add(new Participation("Kitzbühel", "Hermann Maier", 2));
participations.add(new Participation("Kitzbühel", "Benni Raich", 3));

participations.print();
```

Erwarteter Output:

```
1 Marcel Hirscher (Kitzbühel)
2 Hermann Maier (Kitzbühel)
3 Benni Raich (Kitzbühel)
```

#### LookupRacer

```
Participations participations = new Participations(100);
String lookupName = "Marcel Hirscher";
Participation lookupParticipation = new Participation("Kitzbühel", "Marcel Hirscher", 1);
String lookupWrongName = "aldskjfhalsdhflajhsdf";

participations.add(lookupParticipation);
participations.add(new Participation("Kitzbühel", "Hermann Maier", 2));
participations.add(new Participation("Kitzbühel", "Benni Raich", 3));

System.out.println(participations.lookupRacer(lookupName) == lookupParticipation ? "true" : "false");
System.out.println(participations.lookupRacer(lookupWrongName) == null ? "true" : "false");
```

Erwarteter Output:

```
true
true
```

#### Modified Constructor

```
Participations participations = new Participations(100);

participations.add(new Participation("Kitzbühel1", "Marcel Hirscher", 1));
participations.add(new Participation("Kitzbühel2", "Hermann Maier", 2));
participations.add(new Participation("Kitzbühel3", "Benni Raich", 3));

Participations testParticipations = new Participations(participations, "Kitzbühel1", "Kitzbühel2");

testParticipations.print();
```

Erwarteter Output:

```
1 Marcel Hirscher (Kitzbühel1)
2 Hermann Maier (Kitzbühel2)
```

### Class Participations1

#### Overload Test

```
Participations1 participationsOverload = new Participations1(2);

participationsOverload.add(new Participation("Kitzbühel", "Marcel Hirscher", 1));
participationsOverload.add(new Participation("Kitzbühel", "Hermann Maier", 2));
participationsOverload.add(new Participation("Kitzbühel", "Benni Raich", 3));
```

Erwarteter Output:

```
Beliebiger Fehler
```

#### Print

```
Participations1 participations = new Participations1();

participations.add(new Participation("Kitzbühel", "Marcel Hirscher", 1));
participations.add(new Participation("Kitzbühel", "Hermann Maier", 2));
participations.add(new Participation("Kitzbühel", "Benni Raich", 3));

MyMiniTestSuite.changeOutToFile();
participations.print();
```

Erwarteter Output:

```
1 Marcel Hirscher (Kitzbühel)
2 Hermann Maier (Kitzbühel)
3 Benni Raich (Kitzbühel)
```

#### LookupRacer

```
Participations1 participations = new Participations1();
String lookupName = "Marcel Hirscher";
Participation lookupParticipation = new Participation("Kitzbühel", lookupName, 1);
String lookupWrongName = "aldskjfhalsdhflajhsdf";

participations.add(lookupParticipation);
participations.add(new Participation("Kitzbühel", "Hermann Maier", 2));
participations.add(new Participation("Kitzbühel", "Benni Raich", 3));

System.out.println(participations.lookupRacer(lookupName) == lookupParticipation)
System.out.println(participations.lookupRacer(lookupWrongName) == null)
```

Erwarteter Output:

```
true
true
```

#### First

```
Participations1 participations = new Participations1();
Participations1 participationsEmpty = new Participations1();
Participation first = new Participation("Kitzbühel", "Marcel Hirscher", 1);

participations.add(first);
participations.add(new Participation("Kitzbühel", "Hermann Maier", 2));
participations.add(new Participation("Kitzbühel", "Benni Raich", 3));

System.out.println(participations.first() == first) System.out.println(participationsEmpty.first() == null)
```

Erwarteter Output:

```
true
true
```

#### Print with Constraints

```
Participations1 participations = new Participations1();

participations.add(new Participation("Kitzbühel", "Marcel Hirscher", 1));
participations.add(new Participation("Kitzbühel", "Hermann Maier", 2));
participations.add(new Participation("Kitzbühel", "Benni Raich", 3));
participations.add(new Participation("Schladming", "Benni Raich", 4));
participations.add(new Participation("Schladming", "Marcel Hirscher", 5));

MyMiniTestSuite.changeOutToFile();
participations.print(3);
```

Erwarteter Output:

```
1 Marcel Hirscher (Kitzbühel)
2 Hermann Maier (Kitzbühel)
3 Benni Raich (Kitzbühel)
```

### Class Participations2

#### Overload Test

```
Participations2 participationsOverload = new Participations2(2);

participationsOverload.add(new Participation("Kitzbühel", "Marcel Hirscher", 1));
participationsOverload.add(new Participation("Kitzbühel", "Hermann Maier", 2));
participationsOverload.add(new Participation("Kitzbühel", "Benni Raich", 3));
```

Erwarteter Output:

```
Beliebiger Fehler
```

#### Print

```
Participations2 participations = new Participations2();

Participations2 participations = new Participations2();

participations.add(new Participation("Kitzbühel", "Marcel Hirscher", 1));
participations.add(new Participation("Kitzbühel", "Hermann Maier", 2));
participations.add(new Participation("Kitzbühel", "Benni Raich", 3));
participations.add(new Participation("Schladming", "Benni Raich", 4));
participations.add(new Participation("Schladming", "Marcel Hirscher", 5));

MyMiniTestSuite.changeOutToFile();
participations.print();

Erwarteter Output:

```
3 Benni Raich (Kitzbühel)
4 Benni Raich (Schladming)
2 Hermann Maier (Kitzbühel)
1 Marcel Hirscher (Kitzbühel)
5 Marcel Hirscher (Schladming)
```
```

#### LookupRacer

```
Participations2 participations = new Participations2();
String lookupName = "Marcel Hirscher";
Participation lookupParticipation = new Participation("Kitzbühel", lookupName, 1);
String lookupWrongName = "aldskjfhalsdhflajhsdf";

participations.add(lookupParticipation);
participations.add(new Participation("Kitzbühel", "Hermann Maier", 2));
participations.add(new Participation("Kitzbühel", "Benni Raich", 3));
participations.add(new Participation("Schladming", "Benni Raich", 4));
participations.add(new Participation("Schladming", lookupName, 5));

System.out.println(participations.lookupRacer(lookupName) == lookupParticipation) System.out.println(participations.lookupRacer(lookupWrongName) == null));
```

Erwarteter Output:

```
true
true
```

#### Print with Constraints

```
Participations2 participations = new Participations2();

participations.add(new Participation("Kitzbühel", "Marcel Hirscher", 1));
participations.add(new Participation("Kitzbühel", "Hermann Maier", 2));
participations.add(new Participation("Kitzbühel", "Benni Raich", 3));
participations.add(new Participation("Schladming", "Benni Raich", 4));
participations.add(new Participation("Schladming", "Marcel Hirscher", 5));

MyMiniTestSuite.changeOutToFile();
participations.print(3);
```

Erwarteter Output:

```
3 Benni Raich (Kitzbühel)
2 Hermann Maier (Kitzbühel)
1 Marcel Hirscher (Kitzbühel)
```

### Class CharStack1

#### Pop

```
CharStack1 cs = new CharStack1();

cs.push('y');
cs.push('e');
cs.push('h');


System.out.println(cs.pop());
System.out.println(cs.pop());
System.out.println(cs.pop());
System.out.println(cs.pop());
```

Erwarteter Output:

```
h
e
y

```

#### Push

```
CharStack1 cs1 = new CharStack1();
CharStack1 cs2 = new CharStack1();
CharStack1 cs3 = new CharStack1();

cs2.push('y');
cs2.push('e');
cs2.push('h');
cs2.pop();

cs3.push('y');
cs3.push('e');
cs3.push('h');
cs3.pop();
cs3.pop();
cs3.pop();
cs3.pop();
cs3.pop();
cs3.pop();

System.out.println(cs1.isEmpty());
System.out.println(cs2.isEmpty());
System.out.println(cs3.isEmpty());
```

Erwarteter Output:

```
true
false
true
```
