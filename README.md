# Factory-Method
Se implementa en Git, un cpackage com.arquitecturajava;
 package com.arquitecturajava;
 
public abstract class Factura {
 
private int id;
 private double importe;
 public int getId() {
 return id;
 }
 public void setId(int id) {
 this.id = id;
 }
 public double getImporte() {
 return importe;
 }
 public void setImporte(double importe) {
 this.importe = importe;
 }
 
 public abstract double getImporteIva();
}
package com.arquitecturajava;
 
public class FacturaIva extends Factura{
 
@Override
 public double getImporteIva() {
 // TODO Auto-generated method stub
 return getImporte()*1.21;
 }
 
}
package com.arquitecturajava;
 
public class FacturaIvaReducido extends Factura{
 
@Override
 public double getImporteIva() {
 // TODO Auto-generated method stub
 return getImporte()*1.07;
 }
 
}


package com.arquitecturajava;
 
public class FactoriaFacturas {
 
public static Factura getFactura(String tipo) {
 
 if (tipo.equals("iva")) {
 
 return new FacturaIva();
 }
 else {
 return new FacturaIvaReducido();
 }
 
 }
}


package com.arquitecturajava;
 
public class Principal {
 
 public static void main(String[] args) {
 
 Factura f= FactoriaFacturas.getFactura("iva");
 f.setId(1);
 f.setImporte(100);
 System.out.println(f.getImporteIva());
 }
 
}
