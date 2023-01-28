add_but_fail_if_exists(Fact,KB,[Fact|KB]) :- \+member(Fact,KB).
   
fwd_chain(KB,KBFinal,"forall x: man(x) -> mortal(x)") :-
   member(man(X),KB),
   add_but_fail_if_exists(mortal(X),KB,KB2),
   !,
   fwd_chain(KB2,KBFinal,_).

fwd_chain(KB,KBFinal,"forall x: man(x),woman(y),(married(x,y);married(y,x)) -> needles(y,x)") :-
   member(man(X),KB),
   member(woman(Y),KB),
   (member(married(X,Y),KB);member(married(Y,X),KB)),
   add_but_fail_if_exists(needles(Y,X),KB,KB2),
   !,   
   fwd_chain(KB2,KBFinal,_).
      
fwd_chain(KB,KB,"nothing to deduce anymore").

rt(KBin,KBout) :- fwd_chain(KBin,KBout,_).
