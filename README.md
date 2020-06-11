# PROYECTO-TEC
Codigo para proyecto final de TAP
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;
import javax.swing.table.DefaultTableModel;
import java.util.Calendar; 
import java.io.*;
import java.net.*;
import javax.sound.sampled.*;

public class Proyecto
{  
String [] principal = {"Nombre","Destino","Pago","Usuario","SubTotal"};	
DefaultTableModel ventas = new DefaultTableModel();		
JTable tabla = new JTable(ventas);
String []principalv={"Num.Viaje","Total"};
DefaultTableModel ingresos=new DefaultTableModel();
JTable tablav=new JTable(ingresos);
JPasswordField pass,ca,c1;
JButton b1,a1,a2,a3,a4,a5,a6,a7,a8,a9,a,agregar,oki;
String contra,pre1;
JFrame vp,ven,ventb,vc,venc,venv,impresion;
int precio=0;JLabel et;
JMenuItem mision,vision,acerca,open,campass,cerrar,cal;
boolean as1=false,as2=false,as3=false,as4=false,as5=false,as6=false,as7=false,as8=false,as9=false;
JButton salir,nuevar,consul,face,twit,whats,nb,re,inv;
JComboBox des; JCheckBox imp;
JRadioButton efec,tar,com,est;
int total=0,totalv=0,numv=0;
ButtonGroup bg,bc;
String usuario,pagos,nombre,destino,preci,id,t,idc;
JTextField opci,tpagos,cambiod;
JTextField reloj,fecha,prec,nom;
Calendar calendario; 
int dia, mes, año, hora, minutos, segundos,temp,cv=0,cvv=0,cam,tpago; 
Icon imagen=new ImageIcon("cerrar.png");
Icon m=new ImageIcon("guardar.png");
Icon date=new ImageIcon("datos.png");
   	
    public Proyecto() 
    { 
    	principio("admin");
    }
    void principio(String password)
    {
     idc=password;
	  vp=new JFrame("AutoTransportes Pochutla");
      vp.setBounds(0,5,1360,720);
      vp.setIconImage(new ImageIcon("icon.jpg").getImage());
      Icon fondo = new ImageIcon("android.png");
      JLabel eti=new JLabel(fondo);
      vp.add(eti);
      
      Icon ima=new ImageIcon("perfil.png");
      JLabel perfil=new JLabel(ima);
      perfil.setBounds(505,100,305,190);
	  eti.add(perfil);
	
	JLabel emp=new JLabel();
	emp.setBounds(520,280,400,60);
	emp.setFont(new Font("Arial",Font.BOLD,22));
	emp.setForeground(Color.WHITE);
	emp.setText("AutoTransportes Pochutla");
    eti.add(emp);
      
    pass=new JPasswordField();
    pass.setBounds(510,350,200,35);
    eti.add(pass);
    
    b1=new JButton("OK");
    b1.setBounds(720,350,80,35);
   	b1.setVisible(true);
    eti.add(b1);
    
    man acces=new man(); 
    b1.addActionListener(acces);
      
	vp.setResizable(false);
    vp.setVisible(true);	
    }
public  class man implements ActionListener
		{
   			 public void actionPerformed(ActionEvent ea)
   				 {  
   				 	contra=pass.getText();
   				 	if(contra.equals(idc))
   				 	{ vp.dispose(); 
   				 		try{
   				 			Clip sonido=AudioSystem.getClip();
   				 			sonido.open(AudioSystem.getAudioInputStream(new File("inicio.wav")));
   				 			sonido.start();
   				 			Thread.sleep(50);
   				 		}
   				 		catch(Exception w){
   				 			System.out.println("" +w);
   				 		}
   				 	 venp();
    		   		}
    		   		else{
    		   				try{
   				 			Clip sonido=AudioSystem.getClip();
   				 			sonido.open(AudioSystem.getAudioInputStream(new File("error.wav")));
   				 			sonido.start();
   				 		}
   				 		catch(Exception q){
   				 			System.out.println("" +q);
   				 		}
    		   		JOptionPane.showMessageDialog(null,"CONTRASEÑA INCORRECTA");
    		   		pass.setText("");
    		   	    }
   				 }
		}

 public void venp()
{
ven=new JFrame("AutoTransportes Pochutla");
ven.setBounds(0,5,1360,720);
ven.setIconImage(new ImageIcon("icon.jpg").getImage());
 et=new JLabel();
ven.add(et);
   
    JMenuBar mb1=new JMenuBar();
    mb1.setBounds(0,0,400,50);
	JMenuItem view=new JMenu("Ver");
    	mb1.add(view);
    	open=new JMenuItem("Ingresos");
    	view.add(open);    
    JMenu edicion=new JMenu("Edicion");
    mb1.add(edicion);
    campass=new JMenuItem("Cambiar Contraseña");
    edicion.add(campass);
    JMenu sesion=new JMenu("Sesion");
    cerrar=new JMenuItem("Cerrar");
    sesion.add(cerrar);
    mb1.add(sesion);
    JMenu herramientas=new JMenu("Herramientas");
    cal=new JMenuItem("Calculadora");
    herramientas.add(cal);
    mb1.add(herramientas);
     JMenu help=new JMenu("Ayuda");
    	mb1.add(help);
     mision=new JMenuItem("Mision");
    	help.add(mision);
     vision=new JMenuItem("Vision");
    	help.add(vision);
     acerca=new JMenuItem("Acerca de");
    	help.add(acerca);
    
    ven.setJMenuBar(mb1);
    
   men menus=new men();
   open.addActionListener(menus);
   mision.addActionListener(menus);
   vision.addActionListener(menus);
   acerca.addActionListener(menus);
   campass.addActionListener(menus);
   cerrar.addActionListener(menus);
   cal.addActionListener(menus);
   a1=new JButton("A1");
   a1.setBounds(100,50,70,130);
   if(as1==false)
   {a1.setBackground(Color.LIGHT_GRAY);}
   else
   {a1.setBackground(Color.WHITE);}
   et.add(a1);
   
   a2=new JButton("A2");
   a2.setBounds(180,50,70,130);
   if(as2==false)
   {a2.setBackground(Color.LIGHT_GRAY);}
   else
   	{a2.setBackground(Color.WHITE);}
   et.add(a2);
  
   a3=new JButton("A3");
   a3.setBounds(260,50,70,130);
   if(as3==false)
   { a3.setBackground(Color.LIGHT_GRAY);}
   else
   {a3.setBackground(Color.WHITE);}
   et.add(a3);
    
   a4=new JButton("A4");
   a4.setBounds(100,190,70,130);
   if(as4==false)
   {a4.setBackground(Color.LIGHT_GRAY);}
   else
   {a4.setBackground(Color.WHITE);}
   et.add(a4);
   
    a5=new JButton("A5");
   a5.setBounds(180,190,70,130);
   if(as5==false)
   {a5.setBackground(Color.LIGHT_GRAY);}
   else
   {a5.setBackground(Color.WHITE);}
   et.add(a5);
   
    a6=new JButton("A6");
   a6.setBounds(260,190,70,130);
   if(as6==false)
   {a6.setBackground(Color.LIGHT_GRAY);}
   else
   {
   a6.setBackground(Color.WHITE);
   }
   et.add(a6);
   
   a7=new JButton("A7");
   a7.setBounds(100,330,70,130);
   if(as7==false)
   {a7.setBackground(Color.LIGHT_GRAY);}
   else
   {a7.setBackground(Color.WHITE);
   }
   et.add(a7);
    
   a8=new JButton("A8");
   a8.setBounds(180,330,70,130);
   if(as8==false)
   {
   a8.setBackground(Color.LIGHT_GRAY);}
   else
   {
   a8.setBackground(Color.WHITE);
   }
   et.add(a8);
   
   a9=new JButton("A9");
   a9.setBounds(260,330,70,130);
   if(as9==false)
   {
   a9.setBackground(Color.LIGHT_GRAY);
   }
   else
   {
   	a9.setBackground(Color.WHITE);
   }
   et.add(a9);

a1.addActionListener(menus);
a2.addActionListener(menus);
a3.addActionListener(menus);
a4.addActionListener(menus);
a5.addActionListener(menus);
a6.addActionListener(menus);
a7.addActionListener(menus);
a8.addActionListener(menus);
a9.addActionListener(menus);

   JLabel auto=new JLabel();
   auto.setBounds(500,50,400,50);
   auto.setFont(new Font("Arial",Font.TYPE1_FONT,30));
   auto.setForeground(Color.ORANGE);
   auto.setText("AutoTransporte Pochutla");
   et.add(auto);

   JLabel di=new JLabel();
   di.setBounds(460,200,500,50);
   di.setFont(new Font("Arial",Font.LAYOUT_LEFT_TO_RIGHT,22));
   di.setForeground(Color.GREEN);
   di.setText("Lazaro Cardenas ,San Pedro Pochutla,Oax");
   et.add(di);
   
   JLabel com=new JLabel();
   com.setBounds(460,280,500,50);
   com.setFont(new Font("Arial",Font.LAYOUT_LEFT_TO_RIGHT,22));
   com.setForeground(Color.RED);
   com.setText("Viaje Seguro Con Una Comodidad Perfecta");
   et.add(com);
   JLabel re=new JLabel();
   re.setBounds(950,50,200,50);
   re.setFont(new Font("Arial",Font.PLAIN,20));
   re.setForeground(Color.DARK_GRAY);
   re.setText("Hora:");
   et.add(re);
   JLabel fe=new JLabel();
   fe.setBounds(950,90,200,50);
   fe.setFont(new Font("Arial",Font.PLAIN,20));
   fe.setForeground(Color.DARK_GRAY);
   fe.setText("Fecha:");
   et.add(fe);
   //////////reloj///////
   reloj=new JTextField();
   reloj.setBounds(1020,50,200,40);
   fecha=new JTextField();
   fecha.setBounds(1020,95,200,40);
   reloj();
   et.add(reloj);
   et.add(fecha);
   //////////////////////
   Icon usu=new ImageIcon("bg.png");
   JLabel bg=new JLabel(usu);
   bg.setBounds(950,160,270,180);
   JLabel u=new JLabel();
   u.setBounds(995,257,250,50);
   u.setFont(new Font("Arial",Font.LAYOUT_LEFT_TO_RIGHT,21));
   u.setForeground(Color.darkGray);
   u.setText("Usuario: Administrador");
   et.add(u);
   et.add(bg);
   Icon use=new ImageIcon("user.png");
   JLabel user=new JLabel(use);
   user.setBounds(950,255,40,50);
   et.add(user);
   
   consul=new JButton("Ver Ingresos",date);
   consul.setBounds(915,584,160,50);
   et.add(consul);
   consul.addActionListener(menus);
   
   Icon book=new ImageIcon("facebook.png");
   face=new JButton(book);
   face.setBounds(950,150,70,70);
   et.add(face);
  
  Icon twitter=new ImageIcon("twitter.png");
  twit=new JButton(twitter);
  twit.setBounds(1050,150,70,70);
  et.add(twit);
  Icon whattsapp=new ImageIcon("whattsapp.png");
  whats=new JButton(whattsapp);
  whats.setBounds(1150,150,70,70);
  whats.setBackground(Color.white);
  et.add(whats);
  
  urls browser=new urls();
  face.addActionListener(browser);
  whats.addActionListener(browser);
  twit.addActionListener(browser);
  Icon nv=new ImageIcon("new.png");
  nuevar=new JButton("Nuevo Viaje",nv);
  nuevar.setBounds(1080,333,138,40);
  et.add(nuevar);
  nuevar.addActionListener(new ActionListener()	
		{	public void actionPerformed(ActionEvent evt)
							{   numv=numv+1; 
								String to=Integer.toString(total);
								String nb=Integer.toString(numv);
								String[]nuevo={nb,"$"+to};
								ingresos.addRow(nuevo);
							
								for(int i=ventas.getRowCount() -1;i>=0;i--)
									{	ventas.removeRow(i);
										total=0;
										opci.setText("");
									}
							  if(venc!=null)
   				 	 			{
   				 	 				venc.dispose();
   				 	 			}
   				 	 		 if(venv!=null)
   				 	 			{
   				 	 				venv.dispose();
   				 	 			}
								cvv=cvv+1;
								ven.dispose();
					try{
						Thread.sleep(800);
						as1=false;as2=false;as3=false;as4=false;as5=false;as6=false;as7=false;as8=false;as9=false;
						venp(); 
					}
					catch(Exception ev)
					{
						JOptionPane.showMessageDialog(null,"Error Inesperado");
					}
					
				}		
		});
		if(cvv==0)
		{
		    ingresos.setColumnIdentifiers(principalv);
		    tablav.setPreferredScrollableViewportSize(new Dimension(800,450));
			JScrollPane barr = new JScrollPane(tablav);
			barr.setLocation(930,350);
			barr.setSize(300,200);
		    barr.setVisible(false);
	    	et.add(barr);
		}
Icon estre=new ImageIcon("estre.png");
JLabel estrellas=new JLabel(estre);
estrellas.setBounds(520,110,300,80);
et.add(estrellas);

Icon money=new ImageIcon("money.png");
inv=new JButton("Ingresos Por Viajes",money);
inv.setBounds(695,585,200,50);
et.add(inv);
inv.addActionListener(menus);	
JLabel numv=new JLabel();
numv.setBounds(950,336,60,30);
numv.setFont(new Font("Arial",Font.LAYOUT_LEFT_TO_RIGHT,24));
numv.setForeground(Color.darkGray);
numv.setText("Viaje:");
et.add(numv);
JTextField nuv=new JTextField();
nuv.setBounds(1010,336,60,35);
nuv.setBackground(Color.LIGHT_GRAY);
nuv.setFont(new Font("Arial",Font.LAYOUT_LEFT_TO_RIGHT,15));
nuv.setEditable(false);
nuv.addActionListener(cambiar);
nuv.setText(Integer.toString(cvv+1));
et.add(nuv);
		
							JLabel t=new JLabel();
							t.setBounds(100,595,280,30);
							t.setFont(new Font("Arial",Font.LAYOUT_LEFT_TO_RIGHT,24));
							t.setForeground(Color.darkGray);
							t.setText("Total Ingresos:");
							et.add(t);
							
						JTextField tv=new JTextField();
						tv.setBounds(280,594,200,35);
						tv.setBackground(Color.LIGHT_GRAY);
						tv.setFont(new Font("Arial",Font.LAYOUT_LEFT_TO_RIGHT,15));
						tv.setEditable(false);
						tv.addActionListener(cambiar);
						tv.setText("$ "+totalv);
						et.add(tv);
						
						JLabel toti=new JLabel();
						toti.setBounds(100,545,280,30);
						toti.setFont(new Font("Arial",Font.LAYOUT_LEFT_TO_RIGHT,24));
						toti.setForeground(Color.darkGray);
						toti.setText("Total del viaje:");
						et.add(toti);
						opci=new JTextField();
					    opci.setBounds(280,544,200,35);
					    opci.setBackground(Color.LIGHT_GRAY);
						opci.setFont(new Font("Arial",Font.ITALIC,15));
						opci.setEditable(false);
						opci.addActionListener(cambiar);
						opci.setText("$ "+total);
						et.add(opci);

  salir=new JButton("SALIR",imagen);
  salir.setBounds(1095,583,120,50);
  et.add(salir);
  salir.addActionListener(menus);
  ven.setResizable(false);
  ven.setVisible(true);
}
private void reloj() { 
calendario = new java.util.GregorianCalendar();
segundos = calendario.get(Calendar.SECOND); 
javax.swing.Timer timer = new javax.swing.Timer(200, new java.awt.event.ActionListener() { 
@ Override 
public void actionPerformed(ActionEvent ae) { 
java.util.Date actual = new java.util.Date(); 
calendario.setTime(actual); 
dia = calendario.get(Calendar.DAY_OF_MONTH); 
mes = calendario.get(Calendar.MONTH); mes=mes+1;
año = calendario.get(Calendar.YEAR); 
hora = calendario.get(Calendar.HOUR);
temp=calendario.get(Calendar.AM_PM);
minutos = calendario.get(Calendar.MINUTE); 
segundos = calendario.get(Calendar.SECOND);
if(temp==1)
{t="PM";}
else
{t="AM";}
if(hora==0)
{hora=12;}
String hour = String.format("%02d : %02d : %02d %s", hora, minutos, segundos,t); 
String date = String.format("%02d / %02d / %02d", dia, mes, año); 
reloj.setText(hour);
reloj.setForeground(Color.darkGray);
reloj.setBackground(Color.LIGHT_GRAY);
reloj.setFont(new Font("Arial",Font.ITALIC,20));
reloj.setEditable(false);
fecha.setText(date);
fecha.setForeground(Color.darkGray);
fecha.setBackground(Color.LIGHT_GRAY);
fecha.setFont(new Font("Arial",Font.ITALIC,20));
fecha.setEditable(false);
  } 
}); 
timer.start(); 
} 
public class urls implements ActionListener
{
	public void actionPerformed(ActionEvent clic)
	{   if(clic.getSource()==face)
		{
		try{
			Desktop.getDesktop().browse(new URI(""));
		}
		catch(URISyntaxException ex)
		{
			JOptionPane.showMessageDialog(null,"Error Inesperado");
		}
		catch(IOException e)
		{
		JOptionPane.showMessageDialog(null,"Error Inesperado");	
		}
		
		}
		
		if(clic.getSource()==whats)
		{
			try{
			Desktop.getDesktop().browse(new URI(""));
		}
		catch(URISyntaxException ex)
		{
			JOptionPane.showMessageDialog(null,"Error Inesperado");
		}
			catch(IOException e)
		{
		JOptionPane.showMessageDialog(null,"Error Inesperado");	
		}
		
		}
			if(clic.getSource()==twit)
			{
				try
					{
					Desktop.getDesktop().browse(new URI(""));
				}
				catch(URISyntaxException ex)
				{
					JOptionPane.showMessageDialog(null,"Error Inesperado");
				}
			catch(IOException e)
				{
					JOptionPane.showMessageDialog(null,"Error Inesperado");	
				}
			}
	}
}
	public class men implements ActionListener
		{  
			public void actionPerformed(ActionEvent ev)
   				 {  
   				 if(ev.getSource()==inv)
   				 {
   				 	if(cvv==0)
   				 	{
   				 		try{
   				 			Clip sonido=AudioSystem.getClip();
   				 			sonido.open(AudioSystem.getAudioInputStream(new File("exclamacion.wav")));
   				 			sonido.start();
   				 			}
   				 			catch(Exception q)
   				 		  {
   				 			System.out.println("" +q);
   				 			}
   				 	 		JOptionPane.showMessageDialog(null,"Campos vacios,Realize el primer viaje");
   				 	}
   				 	else
   				 	{
   				 	
   				 	if(venv!=null)
   				 	 {
   				 	 	venv.dispose();
   				 	 }
   				 	 venv =new JFrame("Ingresos * Viajes");
   				 		venv.setIconImage(new ImageIcon("icon.jpg").getImage());
   				 			JLabel etiq= new JLabel();
							venv.add(etiq);	
							
							ingresos.setColumnIdentifiers(principalv);
							tablav.setPreferredScrollableViewportSize(new Dimension(800,450));
							JScrollPane barr = new JScrollPane(tablav);
							barr.setLocation(20,20);
							barr.setSize(450,300);
							barr.setVisible(true);
							etiq.add(barr);

					venv.setBounds(430,80,505,450);
					venv.setResizable(true);
					venv.setVisible(true); 
   				 	}
   				 }
   				 if(ev.getSource()==salir)
   					{System.exit(0);}
   				 		
   					if(ev.getSource()==a1)
   					{	if(as1==false)
   						{
   						venb("Asiento 1");ven.dispose();as1=true;
   						}
   						else
   						{
   							try{
   				 			Clip sonido=AudioSystem.getClip();
   				 			sonido.open(AudioSystem.getAudioInputStream(new File("exclamacion.wav")));
   				 			sonido.start();
   				 			}
   				 			catch(Exception q)
   				 		  {
   				 			System.out.println("" +q);
   				 			}
   							if(as1==true && as2==true && as3==true && as4==true  && as5==true && as6==true && as7==true && as8==true  && as9==true)
		   				 		{
   								 	  JOptionPane.showMessageDialog(null,"Todos los asientos ocupados,realize un nuevo viaje ;)");			 	  	
   				 				}
   						 	else
   						 	{
	   						 	JOptionPane.showMessageDialog(null,"Asiento Ocupado, eliga algun otro asiento");
   							 }
   						}		
   					}
   					if(ev.getSource()==a2)
   					{
   						if(as2==false)
   						{
   							venb("Asiento 2");
   							ven.dispose();
   							as2=true;
   						}
   						else
   						{
   							try{
   				 			Clip sonido=AudioSystem.getClip();
   				 			sonido.open(AudioSystem.getAudioInputStream(new File("exclamacion.wav")));
   				 			sonido.start();
   				 			}
   				 			catch(Exception q)
   				 		  {
   				 			System.out.println("" +q);
   				 			}
   							if(as1==true && as2==true && as3==true && as4==true  && as5==true && as6==true && as7==true && as8==true  && as9==true)
		   				 		{
   								 	  JOptionPane.showMessageDialog(null,"Todos los asientos ocupados,realize un nuevo viaje ;)");			 	  	
   				 				}
   						 	else
   						 	{
	   						 	JOptionPane.showMessageDialog(null,"Asiento Ocupado, eliga algun otro asiento");
   							 }
   						}
   					}
   					if(ev.getSource()==a3)
   						{
   						if(as3==false)
   						{
   							venb("Asiento 3");
   							ven.dispose();
   							as3=true;
   						}
   						else
   						{
   							try{
   				 			Clip sonido=AudioSystem.getClip();
   				 			sonido.open(AudioSystem.getAudioInputStream(new File("exclamacion.wav")));
   				 			sonido.start();
   				 			}
   				 			catch(Exception q)
   				 		  {
   				 			System.out.println("" +q);
   				 			}
   							if(as1==true && as2==true && as3==true && as4==true  && as5==true && as6==true && as7==true && as8==true  && as9==true)
		   				 		{
   								 	  JOptionPane.showMessageDialog(null,"Todos los asientos ocupados,realize un nuevo viaje ;)");			 	  	
   				 				}
   						 	else
   						 	{
	   						 	JOptionPane.showMessageDialog(null,"Asiento Ocupado, eliga algun otro asiento");
   							 }
   						}
   					}
   					if(ev.getSource()==a4)
   					{
   						if(as4==false)
   						{
   							venb("Asiento 4");
   							ven.dispose();
   							as4=true;
   						}
   					else
   						{
   							try{
   				 			Clip sonido=AudioSystem.getClip();
   				 			sonido.open(AudioSystem.getAudioInputStream(new File("exclamacion.wav")));
   				 			sonido.start();
   				 			}
   				 			catch(Exception q)
   				 		  {
   				 			System.out.println("" +q);
   				 			}
   							if(as1==true && as2==true && as3==true && as4==true  && as5==true && as6==true && as7==true && as8==true  && as9==true)
		   				 		{
   								 	  JOptionPane.showMessageDialog(null,"Todos los asientos ocupados,realize un nuevo viaje ;)");			 	  	
   				 				}
   						 	else
   						 	{
	   						 	JOptionPane.showMessageDialog(null,"Asiento Ocupado, eliga algun otro asiento");
   							 }
   						}
   					}
   					if(ev.getSource()==a5)
   						{
   						if(as5==false)
   						{
   							venb("Asiento 5");
   							ven.dispose();
   							as5=true;
   						}
   					else
   						{
   							try{
   				 			Clip sonido=AudioSystem.getClip();
   				 			sonido.open(AudioSystem.getAudioInputStream(new File("exclamacion.wav")));
   				 			sonido.start();
   				 			}
   				 			catch(Exception q)
   				 		  {
   				 			System.out.println("" +q);
   				 			}
   							if(as1==true && as2==true && as3==true && as4==true  && as5==true && as6==true && as7==true && as8==true  && as9==true)
		   				 		{
   								 	  JOptionPane.showMessageDialog(null,"Todos los asientos ocupados,realize un nuevo viaje ;)");	
   				 				}
   						 	else
   						 	{
	   						 	JOptionPane.showMessageDialog(null,"Asiento Ocupado, eliga algun otro asiento");
   							 }
   						}
   					}
   					if(ev.getSource()==a6)
   					{
   						if(as6==false)
   						{
   							venb("Asiento 6");
   							ven.dispose();
   							as6=true;
   						}
   					else
   						{
   							try{
   				 			Clip sonido=AudioSystem.getClip();
   				 			sonido.open(AudioSystem.getAudioInputStream(new File("exclamacion.wav")));
   				 			sonido.start();
   				 			}
   				 			catch(Exception q)
   				 		  {
   				 			System.out.println("" +q);
   				 			}
   							if(as1==true && as2==true && as3==true && as4==true  && as5==true && as6==true && as7==true && as8==true  && as9==true)
		   				 		{
   								 	  JOptionPane.showMessageDialog(null,"Todos los asientos ocupados,realize un nuevo viaje ;)");			 	  	
   				 				}
   						 	else
   						 	{
	   						 	JOptionPane.showMessageDialog(null,"Asiento Ocupado, eliga algun otro asiento");
   							 }
   						}
   					}
   					if(ev.getSource()==a7)
   					{
   						if(as7==false)
   						{
   							venb("Asiento 7");
   							ven.dispose();
   							as7=true;
   						}
   					else	
   						{
   							try{
   				 			Clip sonido=AudioSystem.getClip();
   				 			sonido.open(AudioSystem.getAudioInputStream(new File("exclamacion.wav")));
   				 			sonido.start();
   				 			}
   				 			catch(Exception q)
   				 		  {
   				 			System.out.println("" +q);
   				 			}
   							if(as1==true && as2==true && as3==true && as4==true  && as5==true && as6==true && as7==true && as8==true  && as9==true)
		   				 		{
   								 	  JOptionPane.showMessageDialog(null,"Todos los asientos ocupados,realize un nuevo viaje ;)");			 	  	
   				 				}
   						 	else
   						 	{
	   						 	JOptionPane.showMessageDialog(null,"Asiento Ocupado, eliga algun otro asiento");
   							 }
   						}
   					}
   					if(ev.getSource()==a8)
   					{
   						if(as8==false)
   						{
   							venb("Asiento 8");
   							ven.dispose();
   							as8=true;
   						}
   					   else  	
   						{
   							try{
   				 			Clip sonido=AudioSystem.getClip();
   				 			sonido.open(AudioSystem.getAudioInputStream(new File("exclamacion.wav")));
   				 			sonido.start();
   				 			}
   				 			catch(Exception q)
   				 		  {
   				 			System.out.println("" +q);
   				 			}
   							if(as1==true && as2==true && as3==true && as4==true  && as5==true && as6==true && as7==true && as8==true  && as9==true)
		   				 		{
   								 	  JOptionPane.showMessageDialog(null,"Todos los asientos ocupados,realize un nuevo viaje ;)");			 	  	
   				 				}
   						 	else
   						 	{
	   						 	JOptionPane.showMessageDialog(null,"Asiento Ocupado, eliga algun otro asiento");
   							 }
   						}
   					}
   					if(ev.getSource()==a9)
   						{
   							
   						if(as9==false)
   						{
   							venb("Asiento 9");
   							ven.dispose();	
   						}
   					else
   						{
   							try{
   				 			Clip sonido=AudioSystem.getClip();
   				 			sonido.open(AudioSystem.getAudioInputStream(new File("exclamacion.wav")));
   				 			sonido.start();
   				 			}
   				 			catch(Exception q)
   				 		  {
   				 			System.out.println("" +q);
   				 			}
   							if(as1==true && as2==true && as3==true && as4==true  && as5==true && as6==true && as7==true && as8==true  && as9==true)
		   				 		{
   								 	  JOptionPane.showMessageDialog(null,"Todos los asientos ocupados,realize un nuevo viaje ;)");			 	  	
   				 				}
   						 	else
   						 	{
	   						 	JOptionPane.showMessageDialog(null,"Asiento Ocupado, eliga algun otro asiento");
   							 }
   						}
   					}
   					if(ev.getSource()==cal)
   					{
   						Runtime app=Runtime.getRuntime();
   						try{
   							app.exec("C:/Windows/System32/calc.exe");
   						}
   						catch(Exception x){
   							System.out.println(""+x);
   						}
   					}
   					if(ev.getSource()==campass)
   					{  ven.dispose();
   						 vc=new JFrame("Cambio de Contraseña");
   						vc.setBounds(300,100,680,420);
   						vc.setIconImage(new ImageIcon("icon.jpg").getImage());
   						JLabel ec=new JLabel();
   						vc.add(ec);
   						JLabel p=new JLabel();
   						p.setBounds(100,120,200,30);
						p.setFont(new Font("Arial",Font.PLAIN,22));
						p.setForeground(Color.black);
						p.setText("Contraseña Actual:");
						ec.add(p);
						JLabel pp=new JLabel();
						pp.setBounds(100,160,200,30);
						pp.setFont(new Font("Arial",Font.PLAIN,22));
						pp.setForeground(Color.black);
						pp.setText("Nueva contraseña:");
						ec.add(pp);
   						ca=new JPasswordField();
   						ca.setBounds(300,120,200,30);
   						ec.add(ca);
   						c1=new JPasswordField();
   						c1.setBounds(300,160,200,30);
   						ec.add(c1);
   						 
   						nb=new JButton("Guardar",m);
   						nb.setBounds(375,250,125,40);
   						ec.add(nb);
   						
   						re=new JButton("Cancelar",imagen);
   						re.setBounds(100,250,125,40);
   						ec.add(re);
   						min manp=new min();
   						nb.addActionListener(manp);
   						re.addActionListener(manp);
   						
   						vc.setVisible(true);
   						vc.setResizable(false);		
   					}
   					if(ev.getSource()==cerrar)
   					{
   						ven.dispose();
   						principio(idc);
   					}
   					Icon icono=new ImageIcon("inf.png");
   				 	if(ev.getSource()==mision)
   				 	{
   				 		JOptionPane.showMessageDialog( null,
                  			"BRINDAR UN SERVIVIO DE TRANSPORTE EXCELENTE\nLOGRANDO EL LIDERAZGO A BASE DE LA CALIDAD ;)",
                  			"Mision", JOptionPane.PLAIN_MESSAGE,icono );
   				 		}
   					if(ev.getSource()==vision)
   				 	{
   				 		JOptionPane.showMessageDialog( null,
                  			"PRESTAR SERVICIO DE CALIDAD A LOS USUARIOS",
                  			"Vision", JOptionPane.PLAIN_MESSAGE,icono );
   				 	}
   				 	if(ev.getSource()==acerca)
	   				 	{   
   				 			JOptionPane.showMessageDialog( null,
                  			"I.S.C SISTEMAS COMPUTACIONALES\nTELEFONO: 995-102-6534\nSAN PEDRO POCHUTLA OAXACA\nCODIGO POSTAL: 70900\n",
                  			"Acerca de", JOptionPane.PLAIN_MESSAGE,icono);
   				 	}
   				 		if(ev.getSource()==open || ev.getSource()==consul)
   				 	{		
   				 	
   				 	 if(as1==false && as2==false && as3==false && as4==false  && as5==false && as6==false && as7==false && as8==false  && as9==false)
   				 	 {
   				 	 	try{
   				 			Clip sonido=AudioSystem.getClip();
   				 			sonido.open(AudioSystem.getAudioInputStream(new File("exclamacion.wav")));
   				 			sonido.start();
   				 			}
   				 			catch(Exception q)
   				 		  {System.out.println("" +q);}
   				 	 	JOptionPane.showMessageDialog(null,"Campos Vacios,Realize operaciones");
   				 	 }
   				 	 else
   				 	 {	 if(venc!=null)
   				 	 	{
   				 	 		venc.dispose();
   				 	 	}
   				 	 
   				 		 venc =new JFrame("Ingresos");
   				 	   	 venc.setIconImage(new ImageIcon("icon.jpg").getImage());
   				 			JLabel ep= new JLabel();
							venc.add(ep);
							tabla.setEnabled(false);
							ventas.setColumnIdentifiers(principal);
							tabla.setPreferredScrollableViewportSize(new Dimension(800,450));
							JScrollPane barrita = new JScrollPane(tabla);
							barrita.setLocation(20,20);
							barrita.setSize(850,300);
							barrita.setVisible(true);
							ep.add(barrita);
				
							venc.setBounds(390,80,910,450);
							venc.setResizable(true);
							venc.setVisible(true);	
   				 	 }
   				 	}
   			}
		}
		
 public void venb(String var)
 {  
 id=var;
 ventb=new JFrame(var);
 ventb.setBounds(350,50,680,580);
 ventb.setIconImage(new ImageIcon("icon.jpg").getImage());
 JLabel e=new JLabel();
 ventb.add(e);
Icon regre=new ImageIcon("back.png");
 a=new JButton("Atras",regre);
 a.setBounds(50,480,125,36);
 a.setBackground(Color.LIGHT_GRAY);

 e.add(a);
 JLabel autoa=new JLabel();
 autoa.setBounds(165,10,400,30);
 autoa.setFont(new Font("Arial",Font.PLAIN,28));
 autoa.setForeground(Color.ORANGE);
 autoa.setText("AutoTransporte Pochutla");
 e.add(autoa);
   
 JLabel nombre=new JLabel();
 nombre.setBounds(135,60,100,30);
 nombre.setFont(new Font("Arial",Font.PLAIN,22));
 nombre.setForeground(Color.black);
 nombre.setText("Nombre: ");
e.add(nombre);
nom=new JTextField();
nom.setBounds(275,60,220,30);	
nom.addKeyListener(new KeyAdapter()
{
   public void keyTyped(KeyEvent e)
   {
      char c=e.getKeyChar();
      if(Character.isDigit(c))
      {
         e.consume();  
      }
      if(((int)e.getKeyChar()>32 && (int)e.getKeyChar()<=47)||
	    ((int)e.getKeyChar()>=58 && (int)e.getKeyChar()<=64) ||
	    ((int)e.getKeyChar()>=91 && (int)e.getKeyChar()<=96) ||
	    ((int)e.getKeyChar()>=123 && (int)e.getKeyChar()<=255)
	  )
	  {
	  	e.consume();
	  }
   }
});
e.add(nom);

JLabel salida=new JLabel();
salida.setBounds(135,110,400,30);
salida.setFont(new Font("Arial",Font.ITALIC,22));
salida.setForeground(Color.black);
salida.setText("Salida: San Pedro Pochutla");
e.add(salida);

JLabel destino=new JLabel();
destino.setBounds(135,170,150,30);
destino.setFont(new Font("Arial",Font.PLAIN,22));
destino.setForeground(Color.black);
destino.setText("Destino: ");
e.add(destino);

JLabel pagar=new JLabel();
pagar.setBounds(135,335,150,30);
pagar.setFont(new Font("Arial",Font.PLAIN,20));
pagar.setForeground(Color.black);
pagar.setText("Total a pagar: ");
e.add(pagar);

prec=new JTextField();
prec.setBounds(275,335,220,35);
prec.setBackground(Color.LIGHT_GRAY);
prec.setFont(new Font("Arial",Font.ITALIC,15));
prec.setEditable(false);
prec.addActionListener(cambiar);
prec.setText("$ 10");

items mane=new items();
des=new JComboBox();
des.addItem("Crucero Pochutla")	;
des.addItem("El aguacate");
des.addItem("Ciruelo/La Brecha");
des.addItem("Piñal/Cienegal");
des.addItem("Puente de Coyula/santa maria");
des.addItem("Aeropuerto/Santa Cruz");
des.setBounds(275,170,220,30);
des.setSelectedItem("Crucero Pochutla");
des.addItemListener(mane);

e.add(des);
e.add(prec);

JLabel pago=new JLabel();
pago.setBounds(135,220,100,30);
pago.setFont(new Font("Arial",Font.PLAIN,22));
pago.setForeground(Color.black);
pago.setText("Pago:");
e.add(pago);

efec=new JRadioButton("Efectivo");
efec.setBounds(270,220,120,30);
tar=new JRadioButton("Tarjeta");
tar.setBounds(405,220,120,30);
efec.setSelected(true);
bg=new ButtonGroup();
bg.add(efec);
bg.add(tar);

JLabel user=new JLabel();
user.setBounds(135,270,100,30);
user.setFont(new Font("Arial",Font.PLAIN,22));
user.setForeground(Color.black);
user.setText("Usuario:");
e.add(user);

mon maneja=new mon();
com=new JRadioButton("Normal");
com.setBounds(270,270,100,30);
com.setSelected(true);
com.addActionListener(maneja);

est=new JRadioButton("Estudiante");
est.setBounds(405,270,100,30);
est.addActionListener(maneja);

bc=new ButtonGroup();
bc.add(com);
bc.add(est);

e.add(com);
e.add(est);

e.add(efec);
e.add(tar);

JLabel tpago=new JLabel();
tpago.setBounds(135,400,150,30);
tpago.setFont(new Font("Arial",Font.PLAIN,20));
tpago.setForeground(Color.black);
tpago.setText("Total de pago:");
e.add(tpago);

tpagos=new JTextField();
tpagos.setBounds(275,400,160,30);
tpagos.addKeyListener(new KeyAdapter()
{
public void keyTyped(KeyEvent kt)
{
	char c=kt.getKeyChar();
	if((Character.isLetter(c))||(Character.isSpaceChar(c)) )
	{
		kt.consume();	
	}
	if( ((int)kt.getKeyChar()>=32 &&  (int)kt.getKeyChar()<=47)||
	    ((int)kt.getKeyChar()>=58 &&  (int)kt.getKeyChar()<=64)||
	    ((int)kt.getKeyChar()>=91 &&  (int)kt.getKeyChar()<=96)||
	    ((int)kt.getKeyChar()>=123 && (int)kt.getKeyChar()<=255)
	  )
	  {
	  	kt.consume();
	  }
	if((int)kt.getKeyChar()==8)
	{
		cambiod.setText("");
	}
	
}
});
e.add(tpagos);

oki=new JButton("Ok");
oki.setBounds(445,400,50,30);
e.add(oki);

JLabel cambio=new JLabel();
cambio.setBounds(195,483,80,30);
cambio.setFont(new Font("Arial",Font.PLAIN,20));
cambio.setForeground(Color.black);
cambio.setText("Cambio:");
e.add(cambio);

cambiod=new JTextField();
cambiod.setBounds(270,485,100,30);
cambiod.setBackground(Color.LIGHT_GRAY);
cambiod.setFont(new Font("Arial",Font.ITALIC,15));
cambiod.setEditable(false);
cambiod.addActionListener(cambiar);
cambiod.setText("");
e.add(cambiod);

agregar=new JButton("Agregar",m);
agregar.setBackground(Color.LIGHT_GRAY);
agregar.setBounds(530,480,120,35);
e.add(agregar);
agregar.addActionListener(maneja);

a.addActionListener(maneja);
oki.addActionListener(maneja);

imp=new JCheckBox("Imprimir Boleto");
imp.setBounds(390,480,120,35);
e.add(imp);
							if(cv==0)
							{
					     	tabla.setEnabled(false);
							ventas.setColumnIdentifiers(principal);
							tabla.setPreferredScrollableViewportSize(new Dimension(800,450));
							JScrollPane barrita = new JScrollPane(tabla);
							barrita.setLocation(480,50);
							barrita.setSize(450,300);
							barrita.setVisible(false);
							e.add(barrita);
							}
ventb.setVisible(true);
ventb.setResizable(false);

}

public  class mon implements ActionListener
{
	public void actionPerformed(ActionEvent evento)
 		{
			String sel=id;
			destino=(String)des.getSelectedItem();
			nombre=nom.getText();
			if(evento.getSource()==oki)
			{   String val=tpagos.getText();
				if(val.equals("") || (val.trim().length()==0))
				{
				JOptionPane.showMessageDialog(null,"Ingrese cantidad necesaria");	
				}	
			else
			{
					if(destino.equals("Crucero Pochutla"))
						{	precio=10;}
					if(destino.equals("El aguacate"))
						{	precio=15;}
					if(destino.equals("Ciruelo/La Brecha"))
						{	precio=16;}
					if(destino.equals("Piñal/Cienegal"))
						{	precio=18;}
					if(destino.equals("Puente de Coyula/santa maria"))
						{	precio=20;}
					if(destino.equals("Aeropuerto/Santa Cruz"))
					{	precio=25;
						if(est.isSelected())	
					{ precio=precio-5;
					}
					}
             tpago=Integer.parseInt(tpagos.getText());
			if(tpago>=precio)
			{
			cam=tpago-precio;
			cambiod.setText(Integer.toString(cam));
			}
			else
			{
				JOptionPane.showMessageDialog(null,"Ingrese cantidad necesaria");
			}
			
			}
			}
if(evento.getSource()==agregar)
{   String cambio=cambiod.getText();
	if((nombre.equals("") || nombre.trim().length()==0) || (cambio.equals("")||cambio.trim().length()==0))
	{  cambiod.setText("");
		try{
   				 			Clip sonido=AudioSystem.getClip();
   				 			sonido.open(AudioSystem.getAudioInputStream(new File("error.wav")));
   				 			sonido.start();
   				 		}
   				 		catch(Exception q){
   				 			System.out.println("" +q);
   				 		}
		JOptionPane.showMessageDialog(null,"Ingrese campos necesarios");
	
	}
	
	else{	
			ven.dispose();
			if(sel=="Asiento 9")
			{as9=true;
			}
			if(efec.isSelected())
			{ pagos=efec.getText();
			}
			if(tar.isSelected())
			{ pagos=tar.getText();
			}
			if(com.isSelected())
			{ usuario=com.getText();
			}
			if(est.isSelected())	
			{ usuario=est.getText();
			}
			
			if(destino.equals("Crucero Pochutla"))
			{	precio=10;}
			if(destino.equals("Yolina/Juan Diegal"))
			{	precio=15;}
				if(destino.equals("Ciruelo/La Brecha"))
			{	precio=16;}
				if(destino.equals("Piñal/Cienegal"))
			{	precio=18;}
				if(destino.equals("Puente de Coyula"))
			{	precio=20;}
				if(destino.equals("Aeropuerto/Huatulco"))
			{	precio=25;
						if(est.isSelected())	
					{ precio=precio-5;
					}
			}
			    total=total+precio;
			    totalv=totalv+precio;
				preci=Integer.toString(precio);
		cv=cv+1;
		String []nuevacolum={nombre,destino,pagos,usuario,"$"+preci};
		ventas.addRow(nuevacolum);
		
		if(imp.isSelected())
		{
			impresion=new JFrame("Impresion");
			impresion.setBounds(815,135,400,380);
			JLabel etiqueta=new JLabel();
			impresion.add(etiqueta);
			//Icon paper=new ImageIcon("papel.jpg");
			JLabel nm=new JLabel();
			nm.setBounds(20,10,280,30);
			nm.setFont(new Font("Arial",Font.LAYOUT_LEFT_TO_RIGHT,22));
			nm.setForeground(Color.DARK_GRAY);
			nm.setText("Nombre:" + nombre);
			etiqueta.add(nm);
			JLabel dest=new JLabel();
			dest.setBounds(20,50,280,30);
			dest.setFont(new Font("Arial",Font.LAYOUT_LEFT_TO_RIGHT,22));
			dest.setForeground(Color.DARK_GRAY);
			dest.setText("Destino:" + destino);
			etiqueta.add(dest);
			JLabel pago=new JLabel();
			pago.setBounds(20,90,280,30);
			pago.setFont(new Font("Arial",Font.LAYOUT_LEFT_TO_RIGHT,22));
			pago.setForeground(Color.DARK_GRAY);
			pago.setText("Pago:" + pagos);
			etiqueta.add(pago);
			JLabel usuar=new JLabel();
			usuar.setBounds(20,130,280,30);
			usuar.setFont(new Font("Arial",Font.LAYOUT_LEFT_TO_RIGHT,22));
			usuar.setForeground(Color.DARK_GRAY);
			usuar.setText("Usuario:" + usuario);
			etiqueta.add(usuar);
			
			JLabel to=new JLabel();
			to.setBounds(20,170,280,30);
			to.setFont(new Font("Arial",Font.LAYOUT_LEFT_TO_RIGHT,22));
			to.setForeground(Color.DARK_GRAY);
			to.setText("Total: $"+preci);
			etiqueta.add(to);
			String tp=Integer.toString(tpago);
			String ca=Integer.toString(cam);
			JLabel tpa=new JLabel();
			tpa.setBounds(20,210,280,30);
			tpa.setFont(new Font("Arial",Font.LAYOUT_LEFT_TO_RIGHT,22));
			tpa.setForeground(Color.DARK_GRAY);
			tpa.setText("Total de pago:$ "+tpago);
			etiqueta.add(tpa);
			JLabel cami=new JLabel();
			cami.setBounds(20,250,280,30);
			cami.setFont(new Font("Arial",Font.LAYOUT_LEFT_TO_RIGHT,22));
			cami.setForeground(Color.DARK_GRAY);
			cami.setText("Cambio:$ "+ca);
			etiqueta.add(cami);
			
			JButton acept=new JButton("Aceptar");
			acept.setBounds(290,300,80,35);
			acept.addActionListener(new ActionListener()
			{
				public void actionPerformed(ActionEvent im)
				{
					ventb.dispose();
					impresion.dispose();
					venp();
					
				}
			});
			etiqueta.add(acept);
			impresion.setVisible(true);
			impresion.setResizable(false);
		}
	  	else
	  	{
	  		ventb.dispose();
			venp();
		}
	}
}	
			if(evento.getSource()==a)
			{	
				if(sel.equals("Asiento 1"))
				{ as1=false;}
				if(sel.equals("Asiento 2"))
				{ as2=false;}
				if(sel.equals("Asiento 3"))
				{ as3=false;}
				if(sel.equals("Asiento 4"))
				{ as4=false;}
				if(sel.equals("Asiento 5"))
				{ as5=false;}
				if(sel.equals("Asiento 6"))
				{ as6=false;}
				if(sel.equals("Asiento 7"))
				{ as7=false;}
				if(sel.equals("Asiento 8"))
				{ as8=false;}
				if(sel.equals("Asiento 9"))
				{ as9=false;}
							
				ventb.dispose();
				venp();
			} 
			if(evento.getSource()==com & destino.equals("Aeropuerto/Huatulco"))
			{
			  pre1="$ 25";
			  prec.setText(pre1);
			}
			if(evento.getSource()==est & destino.equals("Aeropuerto/Huatulco"))
			{
			  pre1="$ 20";
			  prec.setText(pre1);
			}		 	
 		}
}
public class items implements ItemListener
{
	public void itemStateChanged( ItemEvent e )
     {
     	cambiod.setText("");
			   				 if (e.getSource()==des)  	
			   			{
			   				String seleccionado=(String)des.getSelectedItem();
							if(seleccionado.equals("Crucero Pochutla"))
            				{
            					pre1="$ 10";
            					prec.setText(pre1);
            				}
            				if(seleccionado.equals("Yolina/Juan Diegal"))
            				{
            					pre1="$ 15";
            					prec.setText(pre1);
            				}
            				if(seleccionado.equals("Ciruelo/La Brecha"))
            				{
            					pre1="$ 16";
            					prec.setText(pre1);
            				}
            				if(seleccionado.equals("Piñal/Cienegal"))
            				{
            					pre1="$ 18";
            					prec.setText(pre1);
            				}
            				if(seleccionado.equals("Puente de Coyula"))
            				{
            					pre1="$ 20";
            					prec.setText(pre1);
            				}
            				if(seleccionado.equals("Aeropuerto/Huatulco"))
            				{
            					if(est.isSelected())
            					{
            					pre1="$ 20";
            					prec.setText(pre1);
            					}
            					else
            					{
            					pre1="$ 25";
            					prec.setText(pre1);						
            					}
            				}    			
						}
     }
}
private ActionListener  cambiar = new ActionListener() 
		{	public void actionPerformed(ActionEvent poi ) 
			{	
				((Component) poi.getSource()).transferFocus();
        	}
        };
public static void main (String[] args) 
{
/*try {
      UIManager.setLookAndFeel("com.sun.java.swing.plaf.metal.MetalLookAndFeel");
     } 
     catch (Exception e) 
     {
      e.printStackTrace();
     }*/
	new Proyecto();
}

public class min implements ActionListener
	{
			public void actionPerformed(ActionEvent ev)
			{	
				String ccontra=ca.getText();
				String nuevacontra=c1.getText();
			   if(ev.getSource()==nb)
			   {
			   	 if(ccontra.equals(idc))
			   	 {
			   	 	idc=c1.getText();
			   	 	vc.dispose();
			   	  	principio(nuevacontra);
			   	 }
			   	 else
			   	 { 
			   	 	try{
   				 			Clip sonido=AudioSystem.getClip();
   				 			sonido.open(AudioSystem.getAudioInputStream(new File("error.wav")));
   				 			sonido.start();
   				 		}
   				 		catch(Exception q){
   				 			System.out.println("" +q);
   				 		}
			   	 	JOptionPane.showMessageDialog(null,"Datos Incorrectos, intente nuevamente");
			   	 }
			   }
			   if(ev.getSource()==re)
			   {
			   	vc.dispose();
			   	venp();
			   }
			}
		}
}
