---
title: "safe_cast (C++ bileşen uzantıları) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- safe_cast
- safe_cast_cpp
- stdcli::language::safe_cast
dev_langs:
- C++
helpviewer_keywords:
- safe_cast keyword [C++]
ms.assetid: 4fa688bf-a8ec-49bc-a4c5-f48134efa4f7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 14bcf198d527fae51a579a2aa6e072a4c57424f1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="safecast-c-component-extensions"></a>safe_cast (C++ Bileşen Uzantıları)
`safe_cast` İşlemi başarılı olursa belirtilen ifade belirtilen tür olarak döndürür; Aksi takdirde oluşturur `InvalidCastException`.  
  
## <a name="all-runtimes"></a>Tüm Çalışma Zamanları  
 (Tüm çalışma zamanları için geçerli hiçbir açıklamalar için bu dil özelliği vardır.)  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
[default]:: safe_cast<  
type-id  
>(  
expression  
)  
  
```  
  
### <a name="parameters"></a>Parametreler  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="windows-runtime"></a>Windows Çalışma Zamanı  
 `safe_cast`Belirtilen ifade türü değiştirmenize izin verir. Burada tam olarak bir değişken veya belirli türüne dönüştürülebilir olmalıdır parametresi beklediğiniz durumlarda, geliştirme sırasında programlama hatalarını algılamak için bir try-catch bloğu olmadan safe_cast kullanabilirsiniz. Daha fazla bilgi için bkz: [atama (C + +/ CX)](http://msdn.microsoft.com/library/windows/apps/hh755802.aspx).  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
[default]:: safe_cast<  
type-id  
>(  
expression  
)  
  
```  
  
### <a name="parameters"></a>Parametreler  
 *tür kimliği*  
 Dönüştürme türü *ifade* için. Bir başvuru veya değer türü, bir değer türü veya bir başvuru veya değer türü izleme başvurusu için bir tanıtıcı.  
  
 *ifade*  
 Bir başvuru veya değer türü, bir değer türü veya bir başvuru veya değer türü izleme başvurusu için bir tanıtıcı değerlendiren bir ifade.  
  
### <a name="remarks"></a>Açıklamalar  
 `safe_cast`oluşturur `InvalidCastException` onu dönüştüremiyorsa *ifade* tarafından belirtilen türe *türü kimliği*. Yakalamak için `InvalidCastException`, belirtin [/EH (özel durum işleme modeli)](../build/reference/eh-exception-handling-model.md) derleyici seçeneği ve bir try/catch deyimi kullanır.  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği: **/ZW**  
  
### <a name="examples"></a>Örnekler  
 **Örnek**  
  
 Aşağıdaki kod örneğinde nasıl kullanılacağı ortaya `safe_cast` Windows çalışma zamanı.  
  
```cpp#  
// safe_cast_ZW.cpp  
// compile with: /ZW /EHsc  
  
using namespace default;  
using namespace Platform;  
  
interface class I1 {};  
interface class I2 {};  
interface class I3 {};  
  
ref class X : public I1, public I2 {};  
  
int main(Array<String^>^ args) {  
   I1^ i1 = ref new X;  
   I2^ i2 = safe_cast<I2^>(i1);   // OK, I1 and I2 have common type: X  
   // I2^ i3 = static_cast<I2^>(i1);   C2440 use safe_cast instead  
   try {  
      I3^ i4 = safe_cast<I3^>(i1);   // Fails because i1 is not derived from I3.  
   }   
   catch(InvalidCastException^ ic) {  
     wprintf(L"Caught expected exception: %s\n", ic->Message);  
   }  
}  
```  
  
 **Output**  
  
```Output  
Caught expected exception: InvalidCastException  
```  
  
## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı 
 `safe_cast`ifade türü değiştirip doğrulanabilen MSIL kodu oluşturmak sağlar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
[cli]:: safe_cast<  
type-id  
>(  
expression  
)  
  
```  
  
### <a name="parameters"></a>Parametreler  
 *tür kimliği*  
 Bir başvuru veya değer türü, bir değer türü veya bir başvuru veya değer türü izleme başvurusu için bir tanıtıcı.  
  
 *ifade*  
 Bir başvuru veya değer türü, bir değer türü veya bir başvuru veya değer türü izleme başvurusu için bir tanıtıcı değerlendiren bir ifade.  
  
### <a name="remarks"></a>Açıklamalar  
 İfade `safe_cast<` *türü kimliği*`>(`*ifade* `)` işlenen ifade türü ID türündeki bir nesneye dönüştürür.  
  
 Derleyici kabul edeceği bir [static_cast](../cpp/static-cast-operator.md) kabul edeceği birçok yerde bir `safe_cast`.  Ancak, `safe_cast` doğrulanabilen MSIL üretmek için garanti oysa bir `static_cast` doğrulanamaz MSIL üretebilir.  Bkz: [saf ve doğrulanabilen kod (C + +/ CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md) ve [Peverify.exe (PEVerify aracı)](/dotnet/framework/tools/peverify-exe-peverify-tool) doğrulanabilen kod hakkında daha fazla bilgi için.  
  
 Gibi `static_cast`, `safe_cast` kullanıcı tanımlı dönüşümler çağırır.  
  
 Atamaları hakkında daha fazla bilgi için bkz: [atama işleçleri](../cpp/casting-operators.md).  
  
 `safe_cast`Geçerli bir **const_cast** (hemen cast **const**).  
  
 `safe_cast`CLI ad alanıdır.  Bkz: [Platform, varsayılan ve cli ad alanları](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md) daha fazla bilgi için.  
  
 Daha fazla bilgi için **safe_cas**t, bkz:  
  
-   [/ CLR ile C türü atamalar (C + +/ CLI)](../windows/c-style-casts-with-clr-cpp-cli.md)  
  
-   [Nasıl yapılır: C++/CLI üzerinde safe_cast kullanma](../dotnet/how-to-use-safe-cast-in-cpp-cli.md)  

### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği:   **/CLR**  
  
### <a name="examples"></a>Örnekler  
 **Örnek**  
  
 Bir örneği burada derleyici kabul bir `static_cast` ancak kabul bir `safe_cast` ilgisiz arabirim türleri arasında atamaları içindir.  İle `safe_cast`, derleyici bir dönüştürme hatası veremez ve dönüştürme mümkün olup olmadığını görmek için çalışma zamanında denetimi gerçekleştirir  
  
```cpp  
// safe_cast.cpp  
// compile with: /clr  
using namespace System;  
  
interface class I1 {};  
interface class I2 {};  
interface class I3 {};  
  
ref class X : public I1, public I2 {};  
  
int main() {  
   I1^ i1 = gcnew X;  
   I2^ i2 = safe_cast<I2^>(i1);   // OK, I1 and I2 have common type: X  
   // I2^ i3 = static_cast<I2^>(i1);   C2440 use safe_cast instead  
   try {  
      I3^ i4 = safe_cast<I3^>(i1);   // fail at runtime, no common type  
   }   
   catch(InvalidCastException^) {  
      Console::WriteLine("Caught expected exception");  
   }  
}  
```  
  
 **Output**  
  
```Output  
Caught expected exception  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma Zamanı Platformları için Bileşen Uzantıları](../windows/component-extensions-for-runtime-platforms.md)