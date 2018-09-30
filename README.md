# AKKA-tips
1.ActorSelection se = sys.actorSelection("akka://sys/user/findme");
		se.tell(new Identify("sss"), actor);
		//selection对象会自动在内部tell第二个参数的actor,发送一个包含该selection查询到的ActorRef的ActorIdentity	,需要在actor内部接受
2.	Future<Object> future = Patterns. ask( ref, "hello future  ", timeout);  
    发送一个"hello future"到ref,此方式会生成一个零时actor作为sender,在ref内部可以通过getSender().tell(),返回处理结果
