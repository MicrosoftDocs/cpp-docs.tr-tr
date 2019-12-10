---
title: Yönetilen Özel Durumları Kullanmaya İlişkin Temel Kavramlar
ms.date: 11/04/2016
helpviewer_keywords:
- try-catch exception handling, managed applications
- __finally keyword, managed exceptions
- exceptions, managed
- try-catch exception handling
- catch blocks
- throwing exceptions, managed exceptions
- Visual C++, handling managed exceptions
ms.assetid: 40ce8931-1ecc-491a-815f-733b23fcba35
ms.openlocfilehash: cf241d4e599ad58c2e39680d8ed4e4e250b42b18
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988543"
---
# <a name="basic-concepts-in-using-managed-exceptions"></a>Yönetilen Özel Durumları Kullanmaya İlişkin Temel Kavramlar

Bu konu, yönetilen uygulamalarda özel durum işlemeyi tartışır. Diğer bir deyişle, **/clr** derleyici seçeneği ile derlenen bir uygulamadır.

## <a name="in-this-topic"></a>Bu konuda

- [/Clr altında özel durumlar üretiliyor](#vcconbasicconceptsinusingmanagedexceptionsanchor1)

- [CLR uzantıları için try/catch blokları](#vcconbasicconceptsinusingmanagedexceptionsanchor2)

## <a name="remarks"></a>Açıklamalar

**/Clr** seçeneğiyle DERLERSENIZ CLR özel durumlarını ve standart <xref:System.Exception> sınıfı, CLR özel durumlarını işlemek için birçok yararlı yöntem sağlar ve Kullanıcı tanımlı özel durum sınıfları için temel sınıf olarak önerilir.

Bir arabirimden türetilmiş özel durum türleri, **/clr**altında desteklenmez. Ayrıca, ortak dil çalışma zamanı, yığın taşması özel durumlarını yakalamada size izin vermez; yığın taşması özel durumu işlemi sonlandırır.

Yönetilen ve yönetilmeyen uygulamalardaki özel durum işlemede farklılıklar hakkında daha fazla bilgi için, bkz. [yönetilen uzantılar C++altında özel durum işleme davranışı ](../dotnet/differences-in-exception-handling-behavior-under-clr.md).

##  <a name="vcconbasicconceptsinusingmanagedexceptionsanchor1"></a>/Clr altında özel durumlar üretiliyor

C++ Throw IFADESI bir clr türü için tanıtıcı oluşturmak üzere genişletilir. Aşağıdaki örnek özel bir özel durum türü oluşturur ve bu türün bir örneğini oluşturur:

```cpp
// clr_exception_handling.cpp
// compile with: /clr /c
ref struct MyStruct: public System::Exception {
public:
   int i;
};

void GlobalFunction() {
   MyStruct^ pMyStruct = gcnew MyStruct;
   throw pMyStruct;
}
```

Bir değer türü oluşturulmadan önce paketlenmelidir:

```cpp
// clr_exception_handling_2.cpp
// compile with: /clr /c
value struct MyValueStruct {
   int i;
};

void GlobalFunction() {
   MyValueStruct v = {11};
   throw (MyValueStruct ^)v;
}
```

##  <a name="vcconbasicconceptsinusingmanagedexceptionsanchor2"></a>CLR uzantıları için try/catch blokları

Aynı **try**/**catch** blok yapısı hem clr hem de yerel özel durumları yakalamak için kullanılabilir:

```cpp
// clr_exception_handling_3.cpp
// compile with: /clr
using namespace System;
ref struct MyStruct : public Exception {
public:
   int i;
};

struct CMyClass {
public:
   double d;
};

void GlobalFunction() {
   MyStruct^ pMyStruct = gcnew MyStruct;
   pMyStruct->i = 11;
   throw pMyStruct;
}

void GlobalFunction2() {
   CMyClass c = {2.0};
   throw c;
}

int main() {
   for ( int i = 1; i >= 0; --i ) {
      try {
         if ( i == 1 )
            GlobalFunction2();
         if ( i == 0 )
            GlobalFunction();
      }
      catch ( CMyClass& catchC ) {
         Console::WriteLine( "In 'catch(CMyClass& catchC)'" );
         Console::WriteLine( catchC.d );
      }
      catch ( MyStruct^ catchException ) {
         Console::WriteLine( "In 'catch(MyStruct^ catchException)'" );
         Console::WriteLine( catchException->i );
      }
   }
}
```

### <a name="output"></a>Çıkış

```
In 'catch(CMyClass& catchC)'
2
In 'catch(MyStruct^ catchException)'
11
```

### <a name="order-of-unwinding-for-c-objects"></a>Nesneler için C++ geri sarma sırası

Oluşturma işlevi ile işleme işlevi C++ arasında çalışma zamanı yığınında olabilecek yok ediciler içeren tüm nesneler için geri sarma oluşur. CLR türleri yığında ayrıldığından, bu dosyalara geri sarma uygulanmaz.

Oluşturulan özel durum için olayların sırası aşağıdaki gibidir:

1. Çalışma zamanı, özel durumu yakalamak için, bir SEH, bir SEH için bir except filtresi olarak uygun catch yan tümcesini veya SEH durumunu bulmak için yığın gösterir. Catch yan tümceleri, ilk olarak sözcük temelli sırada aranır ve ardından çağrı yığınını dinamik olarak kapatır.

1. Doğru işleyici bulduktan sonra, yığın bu noktaya kadar kaçınar. Yığındaki her bir işlev çağrısı için, kendi yerel nesneleri kaldırılır ve __finally blokları, iç içe geçmiş dışarıya göre yürütülür.

1. Yığın geri alındıktan sonra, catch yan tümcesi yürütülür.

### <a name="catching-unmanaged-types"></a>Yönetilmeyen türleri yakalama

Yönetilmeyen bir nesne türü oluşturulduğunda, <xref:System.Runtime.InteropServices.SEHException>türünde bir özel durumla sarmalanır. Uygun **catch** yan tümcesini ararken iki olasılık vardır.

- Yerel C++ bir tür ile karşılaşılırsa, özel durum sarmalanmış ve karşılaşılan türle karşılaştırılır. Bu karşılaştırma, yerel C++ bir türün normal şekilde yakalanmasına izin verir.

- Ancak, ilk olarak, **şehir özel** durum türünde bir **catch** yan tümcesi veya temel sınıflarından biri incelençalışıyorsa, yan tümce özel durumu ele geçirebilir. Bu nedenle, CLR türlerindeki catch yan tümcelerinden önce yerel C++ türlerin yakalandığı tüm catch yan tümcelerini yerleştirmeniz gerekir.

Aşağıdakilere dikkat edin:

```
catch(Object^)
```

and

```
catch(...)
```

, her ikisi de SEH özel durumları dahil olmak üzere oluşturulan türü yakalar.

Yönetilmeyen bir tür catch (Object ^) tarafından yakalanmışsa, oluşturulan nesneyi yok etmez.

Yönetilmeyen özel durumları oluştururken veya sunarken, **/EHS** veya **/EHa**yerine [/EHsc](../build/reference/eh-exception-handling-model.md) derleyici seçeneğini kullanmanızı öneririz.

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme](../extensions/exception-handling-cpp-component-extensions.md)<br/>
[safe_cast](../extensions/safe-cast-cpp-component-extensions.md)<br/>
[Özel Durum İşleme](../cpp/exception-handling-in-visual-cpp.md)
