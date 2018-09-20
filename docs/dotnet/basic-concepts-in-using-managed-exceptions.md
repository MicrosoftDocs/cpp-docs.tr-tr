---
title: Yönetilen özel durumları kullanmaya ilişkin temel kavramlar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- try-catch exception handling, managed applications
- __finally keyword, managed exceptions
- exceptions, managed
- try-catch exception handling
- catch blocks
- throwing exceptions, managed exceptions
- Visual C++, handling managed exceptions
ms.assetid: 40ce8931-1ecc-491a-815f-733b23fcba35
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: cb94b262967723b9d0ed1c177c9ca7996b30f83a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46448343"
---
# <a name="basic-concepts-in-using-managed-exceptions"></a>Yönetilen Özel Durumları Kullanmaya İlişkin Temel Kavramlar

Bu konuda, özel durum işleme yönetilen uygulamalarda anlatılmaktadır. Diğer bir deyişle, ile derlenen bir uygulamayı **/CLR** derleyici seçeneği.

## <a name="in-this-topic"></a>Bu konuda

- [/ CLR altında özel durum atma](#vcconbasicconceptsinusingmanagedexceptionsanchor1)

- [Try/CLR uzantıları için Catch blokları](#vcconbasicconceptsinusingmanagedexceptionsanchor2)

## <a name="remarks"></a>Açıklamalar

Derleme yaparsanız **/CLR** seçeneği, standart yanı sıra, CLR özel durumları işleyebilir [C++ özel durum işleme](../cpp/cpp-exception-handling.md) ve [yapılandırılmış özel durum işleme](../cpp/structured-exception-handling-c-cpp.md) (SEH). Bir CLR özel bir yönetilen türü tarafından oluşturulan tüm özel durumudur. [System::yönetilen](https://msdn.microsoft.com/library/system.exception.aspx) sınıfı CLR özel durumları işlemek için çok sayıda kullanışlı yöntem sağlar ve kullanıcı tanımlı özel durum sınıfları için temel sınıf olarak önerilir.

Bir arabirimden türetilmiş bir özel durum türlerini yakalamak desteklenmiyor altında **/CLR**. Ayrıca, ortak dil çalışma zamanı, yığın taşması özel durumları yakalamak için izin vermez; yığın taşması özel işlemini sonlandırır.

Yönetilen ve yönetilmeyen uygulamalarda özel durum işleme farkları hakkında daha fazla bilgi için bkz: [özel durum işleme davranışını altında C++ için Yönetilen Uzantılar farklılıkları](../dotnet/differences-in-exception-handling-behavior-under-clr.md).

##  <a name="vcconbasicconceptsinusingmanagedexceptionsanchor1"></a> / CLR altında özel durum atma

C++ throw deyimi bir CLR türü için bir tanıtıcı atmak için genişletilir. Aşağıdaki örnek bir özel durum türü oluşturur ve ardından o türün örneğini oluşturur:

```
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

Bir değer türü, durum önce paketlenmelidir:

```
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

##  <a name="vcconbasicconceptsinusingmanagedexceptionsanchor2"></a> Try/CLR uzantıları için Catch blokları

Aynı **deneyin**/**catch** blok yapısı, CLR hem yerel özel durumları yakalamak için kullanılabilir:

```
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

### <a name="order-of-unwinding-for-c-objects"></a>C++ nesneleri için geriye doğru izleme sırası

Tüm Visual C++ nesneleriyle çalışma zamanı yığını oluşturma ve işleme işlevleri arasında olabilecek yok ediciler için geriye doğru izleme gerçekleşir. CLR Türleri yığında ayrılmış olduğundan, geriye doğru izleme için geçerli değildir.

Oluşturulan özel durum için olayların sırası aşağıdaki gibidir:

1. Çalışma zamanı uygun catch yan tümcesinin veya SEH, söz konusu olduğunda yığın size yol gösterir. bir SEH özel durumu yakalamak için için filtre dışında. Catch yan tümceleri ilk sözcük sırada aranır ve dinamik olarak aşağı çağrı yığını.

1. Yığın doğru işleyicisi bulunduktan sonra o noktaya çözülür. Yığındaki her işlev çağrısı için yerel nesnelerini imha ve __finally blokları, en iyi yürütülür dışa iç içe geçmiş.

1. Catch yan tümcesi, yığın geriye doğru çözülür sonra yürütülür.

### <a name="catching-unmanaged-types"></a>Yönetilmeyen türler yakalama

Yönetilmeyen bir nesne oluşturulduğunda türünde bir özel durum ile sarmalandıktan [System::Runtime.InteropServices::SEHException](https://msdn.microsoft.com/library/system.runtime.interopservices.sehexception.aspx). Uygun ararken **catch** yan tümcesi, iki olasılık vardır.

- Yerel C++ tür karşılaşılırsa özel durum sarmalanmamış ve karşılaştırma türü ile karşılaşıldı. Bu karşılaştırma, normal bir şekilde Yakalanacak yerel C++ tür sağlar.

- Ancak, bir **catch** türünde yan tümce **SEHException** veya tüm temel sınıflarını ilk incelenir, özel durum yan tümcesi durdurur. Bu nedenle, herhangi bir yan tümceleri CLR Türleri catch önce yerel C++ türler ilk catch tüm catch yan tümceleri yerleştirmeniz gerekir.

Aşağıdakilere dikkat edin:

```
catch(Object^)
```

and

```
catch(...)
```

her ikisi de, SEH özel durumları da dahil olmak üzere herhangi bir throw türünü yakalar.

Bir yönetilmeyen türe catch(Object^) tarafından yakalandığında oluşturulan nesne yok etmez.

Özel durumları atma veya yakalama yönetilmeyen kullanmanızı öneririz [/ehsc](../build/reference/eh-exception-handling-model.md) derleyici seçeneği yerine **EHS** veya **/eha**.

## <a name="see-also"></a>Ayrıca Bkz.

[Özel Durum İşleme](../windows/exception-handling-cpp-component-extensions.md)<br/>
[safe_cast](../windows/safe-cast-cpp-component-extensions.md)<br/>
[Özel Durum İşleme](../cpp/exception-handling-in-visual-cpp.md)