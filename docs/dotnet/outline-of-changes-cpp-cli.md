---
title: Değişikliklerin anahattı (C + +/ CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c0bbbd6b-c5c4-44cf-a6ca-c1010c377e9d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: cfdf502d5529232b856f85a031ff90392d7c2ff0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46415128"
---
# <a name="outline-of-changes-ccli"></a>Değişikliklerin Anahattı (C++/CLI)

Bu ana hat, bazı değişiklikler örnekleri Yönetilen Uzantılar'dan dilde c++ için Visual C++ gösterir. Daha fazla bilgi için her bir öğe eşlik eden bağlantısını izleyin.

## <a name="no-double-underscore-keywords"></a>Çift alt çizgi anahtar sözcük

Bir özel durumla önündeki tüm anahtar sözcükleri çift alt çizgi kaldırıldı. Bu nedenle, `__value` olur `value`, ve `__interface` olur `interface`ve benzeri. Kullanıcı kodundaki tanımlayıcılar anahtar sözcükler arasındaki ad çakışmalarına önlemek için anahtar sözcükleri öncelikle bağlamsal olarak kabul edilir.

Bkz: [dil anahtar sözcükleri (C + +/ CLI)](../dotnet/language-keywords-cpp-cli.md) daha fazla bilgi için.

## <a name="class-declarations"></a>Sınıf bildirimleri

Yönetilen Uzantıları söz dizimi:

```
__gc class Block {};                           // reference class
__value class Vector {};                       // value class
__interface I {};                        // interface class
__gc __abstract class Shape {};                // abstract class
__gc __sealed class Shape2D : public Shape {}; // derived class
```

Yeni sözdizimi:

```
ref class Block {};                // reference class
value class Vector {};             // value class
interface class I {};        // interface class
ref class Shape abstract {};       // abstract class
ref class Shape2D sealed: Shape{}; // derived class
```

Bkz: [yönetilen türler (C + +/ CL)](../dotnet/managed-types-cpp-cl.md) daha fazla bilgi için.

## <a name="object-declaration"></a>Nesne bildirimi

Yönetilen Uzantıları söz dizimi:

```
public __gc class Form1 : public System::Windows::Forms::Form {
private:
   System::ComponentModel::Container __gc *components;
   System::Windows::Forms::Button   __gc *button1;
   System::Windows::Forms::DataGrid __gc *myDataGrid;
   System::Data::DataSet  __gc *myDataSet;
};
```

Yeni sözdizimi:

```
public ref class Form1 : System::Windows::Forms::Form {
   System::ComponentModel::Container^ components;
   System::Windows::Forms::Button^ button1;
   System::Windows::Forms::DataGrid^ myDataGrid;
   System::Data::DataSet^ myDataSet;
};
```

Bkz: [CLR başvuru sınıf nesnesi bildirimi](../dotnet/declaration-of-a-clr-reference-class-object.md) daha fazla bilgi için.

### <a name="managed-heap-allocation"></a>Yönetilen yığın ayırma

Yönetilen Uzantıları söz dizimi:

```
Button* button1 = new Button; // managed heap
int *pi1 = new int;           // native heap
Int32 *pi2 = new Int32;       // managed heap
```

Yeni sözdizimi:

```
Button^ button1 = gcnew Button;        // managed heap
int * pi1 = new int;                   // native heap
Int32^ pi2 = gcnew Int32;              // managed heap
```

Bkz: [CLR başvuru sınıf nesnesi bildirimi](../dotnet/declaration-of-a-clr-reference-class-object.md) daha fazla bilgi için.

### <a name="a-tracking-reference-to-no-object"></a>Bir nesne için izleme başvurusu

Yönetilen Uzantıları söz dizimi:

```
// OK: we set obj to refer to no object
Object * obj = 0;

// Error: no implicit boxing
Object * obj2 = 1;
```

Yeni sözdizimi:

```
// Incorrect Translation
// causes the implicit boxing of both 0 and 1
Object ^ obj = 0;
Object ^ obj2 = 1;

// Correct Translation
// OK: we set obj to refer to no object
Object ^ obj = nullptr;

// OK: we initialize obj2 to an Int32^
Object ^ obj2 = 1;
```

Bkz: [CLR başvuru sınıf nesnesi bildirimi](../dotnet/declaration-of-a-clr-reference-class-object.md) daha fazla bilgi için.

## <a name="array-declaration"></a>Dizi bildirimi

CLR dizisi yeniden tasarlandı. Stl benzer `vector` şablon koleksiyonu, ancak arka plandaki haritalar `System::Array` sınıfı - diğer bir deyişle, bir şablon uygulaması değil.

Bkz: [CLR dizisi bildirimi](../dotnet/declaration-of-a-clr-array.md) daha fazla bilgi için.

### <a name="array-as-parameter"></a>Parametre olarak bir dizi

Yönetilen Uzantılar dizisi sözdizimi:

```
void PrintValues( Object* myArr __gc[]);
void PrintValues( int myArr __gc[,,]);
```

Yeni dizi sözdizimi:

```
void PrintValues( array<Object^>^ myArr );
void PrintValues( array<int,3>^ myArr );
```

### <a name="array-as-return-type"></a>Dönüş türü olarak dizi

Yönetilen Uzantılar dizisi sözdizimi:

```
Int32 f() [];
int GetArray() __gc[];
```

Yeni dizi sözdizimi:

```
array<Int32>^ f();
array<int>^ GetArray();
```

### <a name="shorthand-initialization-of-local-clr-array"></a>Yerel CLR dizinin toplu başlatma

Yönetilen Uzantılar dizisi sözdizimi:

```
int GetArray() __gc[] {
   int a1 __gc[] = { 1, 2, 3, 4, 5 };
   Object* myObjArray __gc[] = { __box(26), __box(27), __box(28),
                                 __box(29), __box(30) };

   return a1;
}
```

Yeni dizi sözdizimi:

```
array<int>^ GetArray() {
   array<int>^ a1 = {1,2,3,4,5};
   array<Object^>^ myObjArray = {26,27,28,29,30};

   return a1;
}
```

### <a name="explicit-clr-array-declaration"></a>Açık CLR dizisi bildirimi

Yönetilen Uzantılar dizisi sözdizimi:

```
Object* myArray[] = new Object*[2];
String* myMat[,] = new String*[4,4];
```

Yeni dizi sözdizimi:

```
array<Object^>^ myArray = gcnew array<Object^>(2);
array<String^,2>^ myMat = gcnew array<String^,2>(4,4);
```

Yeni dil: gcnew izleyen açık bir dizi başlatma

```
// explicit initialization list follow gcnew
// is not supported in Managed Extensions
array<Object^>^ myArray =
   gcnew array<Object^>(4){ 1, 1, 2, 3 };
```

## <a name="scalar-properties"></a>Skaler Özellikler

Yönetilen Uzantılar özelliği sözdizimi:

```
public __gc __sealed class Vector {
   double _x;

public:
   __property double get_x(){ return _x; }
   __property void set_x( double newx ){ _x = newx; }
};
```

Yeni özellik sözdizimi:

```
public ref class Vector sealed {
   double _x;

public:
   property double x
   {
      double get()             { return _x; }
      void   set( double newx ){ _x = newx; }
   } // Note: no semi-colon
};
```

Yeni dil: Önemsiz özellikleri

```
public ref class Vector sealed {
public:
   // equivalent shorthand property syntax
   // backing store is not accessible
   property double x;
};
```

Bkz: [özellik bildiriminde](../dotnet/property-declaration.md) daha fazla bilgi için.

## <a name="indexed-properties"></a>Dizini Oluşturulan Özellikler

Yönetilen Uzantılar dizinli özellik sözdizimi:

```
public __gc class Matrix {
   float mat[,];

public:
   __property void set_Item( int r, int c, float value) { mat[r,c] = value; }
   __property int get_Item( int r, int c ) { return mat[r,c]; }
};
```

Yeni dizine alınan özelliğinin sözdizimi:

```
public ref class Matrix {
   array<float, 2>^ mat;

public:
   property float Item [int,int] {
      float get( int r, int c ) { return mat[r,c]; }
      void set( int r, int c, float value ) { mat[r,c] = value; }
   }
};
```

Yeni dil: sınıf düzeyi dizinlenmiş özellik

```
public ref class Matrix {
   array<float, 2>^ mat;

public:
   // ok: class level indexer now
   //     Matrix mat;
   //     mat[ 0, 0 ] = 1;
   //
   // invokes the set accessor of the default indexer

   property float default [int,int] {
      float get( int r, int c ) { return mat[r,c]; }
      void set( int r, int c, float value ) { mat[r,c] = value; }
   }
};
```

Bkz: [özellik dizini bildirimi](../dotnet/property-index-declaration.md) daha fazla bilgi için.

## <a name="overloaded-operators"></a>Aşırı Yüklenmiş İşleçler

Yönetilen Uzantılar işleci aşırı yükleme sözdizimine:

```
public __gc __sealed class Vector {
public:
   Vector( double x, double y, double z );

   static bool    op_Equality( const Vector*, const Vector* );
   static Vector* op_Division( const Vector*, double );
};

int main() {
   Vector *pa = new Vector( 0.231, 2.4745, 0.023 );
   Vector *pb = new Vector( 1.475, 4.8916, -1.23 );

   Vector *pc = Vector::op_Division( pa, 4.8916 );

   if ( Vector::op_Equality( pa, pc ))
      ;
}
```

Yeni işleci aşırı yükleme sözdizimine:

```
public ref class Vector sealed {
public:
   Vector( double x, double y, double z );

   static bool    operator ==( const Vector^, const Vector^ );
   static Vector^ operator /( const Vector^, double );
};

int main() {
   Vector^ pa = gcnew Vector( 0.231, 2.4745, 0.023 );
   Vector^ pb = gcnew Vector( 1.475, 4.8916, -1.23 );

   Vector^ pc = pa / 4.8916;
   if ( pc == pa )
      ;
}
```

Bkz: [aşırı yüklenmiş işleçler](../dotnet/overloaded-operators.md) daha fazla bilgi için.

## <a name="conversion-operators"></a>Dönüşüm İşleçleri

Yönetilen Uzantılar dönüştürme işleci sözdizimi:

```
__gc struct MyDouble {
   static MyDouble* op_Implicit( int i );
   static int op_Explicit( MyDouble* val );
   static String* op_Explicit( MyDouble* val );
};
```

Yeni dönüştürme işleci sözdizimi:

```
ref struct MyDouble {
public:
   static operator MyDouble^ ( int i );
   static explicit operator int ( MyDouble^ val );
   static explicit operator String^ ( MyDouble^ val );
};
```

Bkz: [değişiklikleri dönüştürme işleçleri](../dotnet/changes-to-conversion-operators.md) daha fazla bilgi için.

## <a name="explicit-override-of-an-interface-member"></a>Arabirim Üyesini Açık Geçersiz Kılma

Yönetilen Uzantılar açık geçersiz kılma sözdizimi:

```
public __gc class R : public ICloneable {
   // to be used through ICloneable
   Object* ICloneable::Clone();

   // to be used through an R
   R* Clone();
};
```

Yeni açık bir geçersiz kılma sözdizimi:

```
public ref class R : public ICloneable {
   // to be used through ICloneable
   virtual Object^ InterfaceClone() = ICloneable::Clone;

   // to be used through an R
   virtual R^ Clone();
};
```

Bkz: [arabirim üyesini açık geçersiz kılma](../dotnet/explicit-override-of-an-interface-member.md) daha fazla bilgi için.

## <a name="private-virtual-functions"></a>Özel Sanal İşlevler

Yönetilen Uzantılar özel bir sanal işlev sözdizimi:

```
__gc class Base {
private:
   // inaccessible to a derived class
   virtual void g();
};

__gc class Derived : public Base {
public:
   // ok: g() overrides Base::g()
   virtual void g();
};
```

Yeni özel sanal işlev sözdizimi

```
ref class Base {
private:
   // inaccessible to a derived class
   virtual void g();
};

ref class Derived : public Base {
public:
   // error: cannot override: Base::g() is inaccessible
   virtual void g() override;
};
```

Bkz: [özel sanal işlevler](../dotnet/private-virtual-functions.md) daha fazla bilgi için.

## <a name="clr-enum-type"></a>CLR Numaralandırma Türü

Yönetilen Uzantılar enum sözdizimi:

```
__value enum e1 { fail, pass };
public __value enum e2 : unsigned short  {
   not_ok = 1024,
   maybe, ok = 2048
};
```

Yeni sabit listesi sözdizimi:

```
enum class e1 { fail, pass };
public enum class e2 : unsigned short {
   not_ok = 1024,
   maybe, ok = 2048
};
```

Bu küçük söz dizimsel değişiklik dışında CLR numaralandırma türü davranışını çeşitli şekillerde değiştirildi:

- CLR enum İleri dönük bildiriminin artık desteklenmiyor.

- Yerleşik aritmetik türleri ve nesne sınıfı hiyerarşisi arasında aşırı yükleme çözünürlüğü, Visual C++ ve Yönetilen Uzantılar arasında ters. Bir yan etkisi olarak CLR numaralandırmaları artık örtük olarak aritmetik türlerine dönüştürülür.

- Yeni sözdiziminde, CLR enum Yönetilen Uzantılar'durumunda değil, kendi kapsamı tutar. Daha önce numaralandırıcılar enum kapsayan kapsamda görünür; Şimdi, numaralandırıcılar enum kapsamı içinde kapsüllenir.

Bkz: [CLR numaralandırma türü](../dotnet/clr-enum-type.md) daha fazla bilgi için.

## <a name="removal-of-box-keyword"></a>__Box Anahtar

Yönetilen Uzantılar: kutulama sözdizimi

```
Object *o = __box( 1024 ); // explicit boxing
```

Yeni paketleme sözdizimi:

```
Object ^o = 1024; // implicit boxing
```

Bkz: [bir kutu içinde bir değer tanıtıcı izleme](../dotnet/a-tracking-handle-to-a-boxed-value.md) daha fazla bilgi için.

## <a name="pinning-pointer"></a>Sabitleme işaretçisi

Yönetilen Uzantılar: sabitleme işaretçisi sözdizimi

```
__gc struct H { int j; };

int main() {
   H * h = new H;
   int __pin * k = & h -> j;
};
```

Yeni sabitleme işaretçisi sözdizimi:

```
ref struct H { int j; };

int main() {
   H^ h = gcnew H;
   pin_ptr<int> k = &h->j;
}
```

Bkz: [değer türü anlamları](../dotnet/value-type-semantics.md) daha fazla bilgi için.

## <a name="typeof-keyword-becomes-typeid"></a>__typeof anahtar sözcüğü TypeID haline gelir.

Yönetilen Uzantılar typeof sözdizimi:

```
Array* myIntArray =
   Array::CreateInstance( __typeof(Int32), 5 );
```

Yeni TypeID sözdizimi:

```
Array^ myIntArray =
   Array::CreateInstance( Int32::typeid, 5 );
```

Bkz: [typeof t:: typeid'e gider](../dotnet/typeof-goes-to-t-typeid.md) daha fazla bilgi için.

## <a name="see-also"></a>Ayrıca Bkz.

[C++/CLI Geçiş Öncüsü](../dotnet/cpp-cli-migration-primer.md)<br/>
[Çalışma Zamanı Platformları için Bileşen Uzantıları](../windows/component-extensions-for-runtime-platforms.md)

