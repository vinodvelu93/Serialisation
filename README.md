# Serialisation


import java.io.*;
public class Persist implements Serializable {
  int id;
	 String name;
	Persist(int id,String name){
		this.id=id;
		this.name=name;
		
	}

	public static void main(String[] args) throws IOException {
		
		Persist p=new Persist(24,"prakash");
		
		FileOutputStream fout=new FileOutputStream("D:/b.txt");
		ObjectOutputStream out=new ObjectOutputStream(fout);
		out.writeObject(p);
		
		out.flush();
		out.close();
		System.out.println("success");
	}

	

}
package com.serialisation;

import java.io.*;

public class Depersist{

	public static void main(String[] args) throws Exception {
		// TODO Auto-generated method stub
		FileInputStream fout=new FileInputStream("D:/b.txt");
		ObjectInputStream in=new ObjectInputStream(fout);
		Persist p=(Persist)in.readObject();
		
		in.close();
		System.out.println("the person Name is: "+" "+p.name);
		System.out.println("the person id is: "+p.id);

	}

}
