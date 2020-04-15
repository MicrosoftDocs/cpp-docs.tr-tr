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
ms.openlocfilehash: 6bc1e9c6d40599ae9a821179dcf56dbb7e21bf10
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372524"
---
# <a name="basic-concepts-in-using-managed-exceptions"></a>Yönetilen Özel Durumları Kullanmaya İlişkin Temel Kavramlar

Bu konu, yönetilen uygulamalarda özel durum işleme tartışır. Yani **/clr** derleyici seçeneği ile derlenen bir uygulamadır.

## <a name="in-this-topic"></a>Bu konuda

- [/clr Altında Özel Durumlar Atma](#vcconbasicconceptsinusingmanagedexceptionsanchor1)

- [CLR Uzantıları için Blokları Deneyin/Yakala](#vcconbasicconceptsinusingmanagedexceptionsanchor2)

## <a name="remarks"></a>Açıklamalar

**/clr** seçeneğiyle derlerseniz, CLR özel durumlarını işleyebilir <xref:System.Exception> ve standart sınıf CLR özel durumlarını işlemek için birçok yararlı yöntem sağlar ve kullanıcı tanımlı özel durum sınıfları için taban sınıf olarak önerilir.

Arabirimden türetilen özel durum türlerinin yakalanması **/clr**altında desteklenmez. Ayrıca, ortak dil çalışma süresi yığın taşma özel durumları yakalamak için izin vermez; yığın taşması özel durumu işlemi sonlandırır.

Yönetilen ve yönetilmeyen uygulamalarda özel durum işleme deki farklılıklar hakkında daha fazla bilgi [için, C++ için Yönetilen Uzantılar Altında Özel Durum İşleme DavranışıNdaki Farklılıklar'a](../dotnet/differences-in-exception-handling-behavior-under-clr.md)bakın.

## <a name="throwing-exceptions-under-clr"></a><a name="vcconbasicconceptsinusingmanagedexceptionsanchor1"></a>/clr Altında Özel Durumlar Atma

C++ atma ifadesi clr türüne bir tutamaç atmak için uzatılır. Aşağıdaki örnek özel bir özel durum türü oluşturur ve sonra bu tür bir örnek atar:

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

Bir değer türü atılmadan önce kutulanmalıdır:

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

## <a name="trycatch-blocks-for-clr-extensions"></a><a name="vcconbasicconceptsinusingmanagedexceptionsanchor2"></a>CLR Uzantıları için Blokları Deneyin/Yakala

Aynı **try**/**catch** bloğu yapısı hem CLR hem de yerel özel durumları yakalamak için kullanılabilir:

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

### <a name="order-of-unwinding-for-c-objects"></a>C++ Nesneleri için Gevşeme Sırası

Boşaltma, atma işlevi ile işleme işlevi arasındaki çalışma zamanı yığınında olabilecek yıkıcılara sahip c++ nesneleri için oluşur. CLR türleri yığına ayrıldıkolduğundan, gevşeme onlar için geçerli değildir.

Atılan bir özel durum için olayların sırası aşağıdaki gibidir:

1. Çalışma zamanı, özel durumu yakalamak için uygun catch yan tümcesini bulmak için yığını yürür veya SEH,SEH için bir dış filtre olan SEH durumunda. Catch yan tümceleri önce sözlü sırada aranır, sonra dinamik olarak arama yığınıaşağı.

1. Doğru işleyici bulunduktan sonra, yığın o noktaya kadar çözülir. Yığındaki her işlev çağrısı için, yerel nesneleri destructed ve __finally blokları, en iç içe dışa doğru yürütülür.

1. Yığın çözüldükten sonra, yakalama yan tümcesi yürütülür.

### <a name="catching-unmanaged-types"></a>Yönetilmeyen Türleri Yakalama

Yönetilmeyen bir nesne türü atıldığında, türü <xref:System.Runtime.InteropServices.SEHException>bir özel durum ile sarılır. Uygun **yakalama** yan tümcesi aranırken iki olasılık vardır.

- Yerel bir C++ türüyle karşılaşılırsa, özel durum unwrapped ve karşılaşılan türile karşılaştırıldığında. Bu karşılaştırma, yerel bir C++ türü normal şekilde yakalanmasını sağlar.

- Ancak, **önce SEHException** türünden veya temel sınıflarından herhangi birinin **yakalama** yan tümcesi incelenirse, yan tümce özel durumu keser. Bu nedenle, clr türlerinin herhangi bir catch yan tümcesi önce ana C++ türlerini yakalamak tüm catch yan tümceleri yerleştirmeniz gerekir.

Aşağıdakilere dikkat edin:

```
catch(Object^)
```

ve

```
catch(...)
```

her ikisi de SEH özel durumlar da dahil olmak üzere herhangi bir atılan türü yakalar.

Yönetilmeyen bir tür catch (Object^) tarafından yakalanırsa, atılan nesneyi yok etmez.

Yönetilmeyen özel durumları atarken veya yakalarken, **/EHs** veya **/EHa**yerine [/EHsc](../build/reference/eh-exception-handling-model.md) derleyici seçeneğini kullanmanızı öneririz.

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme](../extensions/exception-handling-cpp-component-extensions.md)<br/>
[safe_cast](../extensions/safe-cast-cpp-component-extensions.md)<br/>
[Özel Durum İşleme](../cpp/exception-handling-in-visual-cpp.md)
