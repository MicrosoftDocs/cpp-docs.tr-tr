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
ms.openlocfilehash: 4eeec5db00ceca5429f4a3a270e1b249a8955249
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230928"
---
# <a name="basic-concepts-in-using-managed-exceptions"></a>Yönetilen Özel Durumları Kullanmaya İlişkin Temel Kavramlar

Bu konu, yönetilen uygulamalarda özel durum işlemeyi tartışır. Diğer bir deyişle, **/clr** derleyici seçeneği ile derlenen bir uygulamadır.

## <a name="in-this-topic"></a>Bu konuda

- [/Clr altında özel durumlar üretiliyor](#vcconbasicconceptsinusingmanagedexceptionsanchor1)

- [CLR uzantıları için try/catch blokları](#vcconbasicconceptsinusingmanagedexceptionsanchor2)

## <a name="remarks"></a>Açıklamalar

**/Clr** seçeneğiyle DERLERSENIZ CLR özel durumlarını işleyebilir <xref:System.Exception> ve standart sınıf, CLR özel durumlarını işlemek için birçok yararlı yöntem sağlar ve Kullanıcı tanımlı özel durum sınıfları için temel sınıf olarak önerilir.

Bir arabirimden türetilmiş özel durum türleri, **/clr**altında desteklenmez. Ayrıca, ortak dil çalışma zamanı, yığın taşması özel durumlarını yakalamada size izin vermez; yığın taşması özel durumu işlemi sonlandırır.

Yönetilen ve yönetilmeyen uygulamalardaki özel durum işlemede farklılıklar hakkında daha fazla bilgi için, [C++ için yönetilen uzantılar altında özel durum Işleme davranışındaki farklılıklar](../dotnet/differences-in-exception-handling-behavior-under-clr.md)bölümüne bakın.

## <a name="throwing-exceptions-under-clr"></a><a name="vcconbasicconceptsinusingmanagedexceptionsanchor1"></a>/Clr altında özel durumlar üretiliyor

C++ throw ifadesi bir CLR türü için tanıtıcı oluşturmak üzere genişletilir. Aşağıdaki örnek özel bir özel durum türü oluşturur ve bu türün bir örneğini oluşturur:

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

## <a name="trycatch-blocks-for-clr-extensions"></a><a name="vcconbasicconceptsinusingmanagedexceptionsanchor2"></a>CLR uzantıları için try/catch blokları

Aynı **`try`** / **`catch`** blok yapısı hem clr hem de yerel özel durumları yakalamak için kullanılabilir:

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

### <a name="output"></a>Çıktı

```
In 'catch(CMyClass& catchC)'
2
In 'catch(MyStruct^ catchException)'
11
```

### <a name="order-of-unwinding-for-c-objects"></a>C++ nesneleri için geri sarma sırası

Oluşturma işlevi ile işleme işlevi arasında çalışma zamanı yığınında olabilecek yok ediciler içeren tüm C++ nesneleri için geriye doğru izleme oluşur. CLR türleri yığında ayrıldığından, bu dosyalara geri sarma uygulanmaz.

Oluşturulan özel durum için olayların sırası aşağıdaki gibidir:

1. Çalışma zamanı, özel durumu yakalamak için, bir SEH, bir SEH için bir except filtresi olarak uygun catch yan tümcesini veya SEH durumunu bulmak için yığın gösterir. Catch yan tümceleri, ilk olarak sözcük temelli sırada aranır ve ardından çağrı yığınını dinamik olarak kapatır.

1. Doğru işleyici bulduktan sonra, yığın bu noktaya kadar kaçınar. Yığındaki her bir işlev çağrısı için, kendi yerel nesneleri kaldırılır ve __finally blokları, iç içe geçmiş dışarıya göre yürütülür.

1. Yığın geri alındıktan sonra, catch yan tümcesi yürütülür.

### <a name="catching-unmanaged-types"></a>Yönetilmeyen türleri yakalama

Yönetilmeyen bir nesne türü oluşturulduğunda, türünde bir özel durumla sarmalanır <xref:System.Runtime.InteropServices.SEHException> . Uygun **`catch`** yan tümceyi ararken iki olasılık vardır.

- Yerel bir C++ türü ile karşılaşılırsa, özel durum sarmalanmış ve karşılaşılan türle karşılaştırılır. Bu karşılaştırma, yerel C++ türünün normal şekilde yakalanmasına izin verir.

- Ancak, ilk olarak, **`catch`** **şehir özel** durum türünde bir yan tümce veya temel sınıflarından herhangi biri incelençalışıyorsa, yan tümce özel durumu ele alınacaktır. Bu nedenle, CLR türlerindeki catch yan tümcelerinden önce yerel C++ türlerini yakalayasağlayan tüm catch yan tümcelerini yerleştirmeniz gerekir.

Aşağıdakilere dikkat edin:

```
catch(Object^)
```

ve

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
