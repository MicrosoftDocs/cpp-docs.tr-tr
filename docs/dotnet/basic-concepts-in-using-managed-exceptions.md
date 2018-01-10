---
title: "Yönetilen özel durumları kullanmaya ilişkin temel kavramlar | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- try-catch exception handling, managed applications
- __finally keyword, managed exceptions
- exceptions, managed
- try-catch exception handling
- catch blocks
- throwing exceptions, managed exceptions
- Visual C++, handling managed exceptions
ms.assetid: 40ce8931-1ecc-491a-815f-733b23fcba35
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 5e2faf56f050610e6c98ff82cdca10333a54fd93
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="basic-concepts-in-using-managed-exceptions"></a>Yönetilen Özel Durumları Kullanmaya İlişkin Temel Kavramlar
Bu konuda, özel durum işleme yönetilen uygulamalarda anlatılmaktadır. Diğer bir deyişle, ile derlenen bir uygulama **/CLR** derleyici seçeneği.  
  
## <a name="in-this-topic"></a>Bu konuda  
  
-   [/ CLR altında özel durumları atma](#vcconbasicconceptsinusingmanagedexceptionsanchor1)  
  
-   [Try/CLR uzantıları Catch blokları](#vcconbasicconceptsinusingmanagedexceptionsanchor2)  
  
## <a name="remarks"></a>Açıklamalar  
 İle derleme yaparsanız **/CLR** seçeneği, CLR özel durumları ve bunun yanı sıra standart işleyebilir [C++ özel durum işleme](../cpp/cpp-exception-handling.md) ve [yapılandırılmış özel durum işleme](../cpp/structured-exception-handling-c-cpp.md) (SEH). Bir CLR özel bir yönetilen türü tarafından oluşturulan özel durumları ' dir. [System::yönetilen](https://msdn.microsoft.com/en-us/library/system.exception.aspx) sınıfı CLR özel durumları işlemek için çok sayıda kullanışlı yöntemler sağlar ve kullanıcı tanımlı özel durum sınıfları için temel sınıf olarak önerilir.  
  
 Özel durum türlerini arabirimden türetilmiş yakalama desteklenmiyor altında **/CLR**. Ayrıca, ortak dil çalışma zamanı yığın taşması özel durumları yakalamak için izin vermiyor; bir yığın taşması özel durumu işlemini sonlandırır.  
  
 Yönetilen ve yönetilmeyen uygulamalarda özel durum işleme farkları hakkında daha fazla bilgi için bkz: [özel durum işleme davranışı altında C++ için Yönetilen Uzantılar farklılıkları](../dotnet/differences-in-exception-handling-behavior-under-clr.md).  
  
##  <a name="vcconbasicconceptsinusingmanagedexceptionsanchor1"></a>/ CLR altında özel durumları atma  
 C++ throw deyimi bir CLR türü için bir tanıtıcı atmak için genişletilir. Aşağıdaki örnek, bir özel durum türü oluşturur ve bu türünün bir örneğini oluşturur:  
  
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
  
 Değer türü, durum önce Kutulu gerekir:  
  
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
  
##  <a name="vcconbasicconceptsinusingmanagedexceptionsanchor2"></a>Try/CLR uzantıları Catch blokları  
 Aynı **deneyin**/**catch** blok yapısı, CLR ve yerel özel durumları yakalamak için kullanılabilir:  
  
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
 Geriye doğru izleme tüm C++ nesneleri oluşturma ve işleme işlevleri arasında çalışma zamanı yığında olabilir Yıkıcılar ile gerçekleşir. CLR Türleri yığında ayrılmış olduğundan, geriye doğru izleme için geçerli değildir.  
  
 Oluşturulan özel durum olayları sırasını aşağıdaki gibidir:  
  
1.  Çalışma zamanı uygun catch yan tümcesinin veya SEH, söz konusu olduğunda arayan yığını anlatılmaktadır bir özel durum yakalamak için SEH için filtre dışında. Yan tümceleri catch sözcük sırada ilk aranır ve dinamik olarak aşağı çağrı yığını.  
  
2.  Yığın doğru işleyici bulunduktan sonra o noktaya unwound. Yığındaki her işlev çağrısı için yerel nesnelerini destructed ve __finally blokları, en iyi yürütülür dışa iç içe geçmiş.  
  
3.  Yığın unwound olduğunda catch yan tümcesi yürütülür.  
  
### <a name="catching-unmanaged-types"></a>Yönetilmeyen türler yakalama  
 Bir yönetilmeyen nesne türü oluştuğunda türünde bir özel durum ile sarılır [System::Runtime.InteropServices::SEHException](https://msdn.microsoft.com/en-us/library/system.runtime.interopservices.sehexception.aspx). İçin uygun ararken **catch** yan tümcesi, iki olasılık vardır.  
  
-   Yerel C++ tür karşılaşılırsa, özel durum sarılmamış ve karşılaştırma türü ile karşılaşıldı. Bu karşılaştırma normal şekilde Yakalanacak yerel C++ tür sağlar.  
  
-   Ancak, bir **catch** yan tümcesinin tür **SEHException** veya temel sınıflarından birini incelenir önce özel durum yan tümcesi durdurur. Bu nedenle, herhangi bir CLR Türleri yan tümcelerinde catch önce yerel C++ türleri ilk catch tüm catch yan tümceleri yerleştirmeniz gerekir.  
  
 Aşağıdakilere dikkat edin:  
  
```  
catch(Object^)  
```  
  
 and  
  
```  
catch(...)  
```  
  
 her ikisi de SEH özel durumlar dahil olmak üzere herhangi bir atılmış türü yakalar.  
  
 Yönetilmeyen tür tarafından catch(Object^) yakalanmışsa atılmış nesnesi yok etmez.  
  
 Özel durumlar atma veya yakalama yönetilmeyen zaman kullanmanız önerilir [/EHsc](../build/reference/eh-exception-handling-model.md) yerine derleyici seçeneği **/EHs** veya **/EHa**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel durum işleme](../windows/exception-handling-cpp-component-extensions.md)   
 [safe_cast](../windows/safe-cast-cpp-component-extensions.md)   
 [Özel Durum İşleme](../cpp/exception-handling-in-visual-cpp.md)