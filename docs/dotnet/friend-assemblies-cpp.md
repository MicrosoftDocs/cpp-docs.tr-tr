---
title: Arkadaş derlemeler (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- friend assemblies, Visual C++
ms.assetid: 8d55fee0-b7c2-4fbe-a23b-dfe424dc71cd
caps.latest.revision: 27
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 6646306092844f11819b81ee076c54db840c618b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="friend-assemblies-c"></a>Arkadaş Derlemeler (C++)
Geçerli çalışma zamanları için *arkadaş derlemeleri* dil özelliği ad alanı kapsamı veya bir veya daha fazla istemci derlemelerine ya da .netmodules için erişilebilir bir derleme bileşeninin genel kapsamda altındadır türleri sağlar.  
  
## <a name="all-runtimes"></a>Tüm Çalışma Zamanları  
 **Açıklamalar**  
  
 (Bu dil özelliği tüm çalışma zamanları desteklenmiyor.)  
  
## <a name="windows-runtime"></a>Windows Çalışma Zamanı  
 **Açıklamalar**  
  
 (Bu dil özelliği Windows çalışma zamanı'nda desteklenmiyor.)  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği: **/ZW**  
  
## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı 
 **Açıklamalar**  
  
#### <a name="to-make-types-at-namespace-scope-or-global-scope-in-an-assembly-component-accessible-to-a-client-assembly-or-netmodule"></a>Ad alanı kapsamı veya genel kapsam türlerini bir derleme bileşeninin istemci derleme veya .netmodule için erişilebilir hale getirmek için  
  
1.  Bileşeninde bir derleme özniteliği belirtin <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>ve istemci derleme veya ad alanı kapsam veya bileşen genel kapsamda türlerini erişecek .netmodule adını geçirin.  Ek öznitelikler belirterek birden çok istemci derleme veya .netmodules belirtebilirsiniz.  
  
2.  İstemci derleme veya kullanarak bileşen bütünleştirilmiş koda başvurduğunuzda .netmodule `#using`, geçirmek `as_friend` özniteliği.  Belirtirseniz `as_friend` özniteliği belirtmediği bir derlemenin `InternalsVisibleToAttribute`, ad alanı kapsam veya bileşen genel kapsamda bir türde erişmeye çalışırsa bir çalışma zamanı özel durum oluşturulur.  
  
 Derleme içeren bir yapı hatasına neden olur <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> bir güçlü ad ancak kullanan istemci derleme özniteliği yok `as_friend` öznitelik yapar.  
  
 Ad alanı kapsamı ve genel kapsam türler için bir istemci derleme veya .netmodule bilinen üye erişilebilirlik hala etkin olsa da.  Örneğin, özel üye erişemiyor.  
  
 Derleme içindeki tüm türler için erişim açıkça verilmelidir.  Örneğin, derleme C erişimi tüm türleri için derleme bir derleme B C bütünleştirilmiş koduna başvuruyor ve derleme B A. derlemede tüm türleri erişimi yok  
  
 Oturum hakkında bilgi — diğer bir deyişle, güçlü bir ad vermek nasıl — Visual C++ Derleyici kullanılarak oluşturulmuş bir derlemeyi bkz [tanımlayıcı ad derlemeleri (derleme imzalama) (C + +/ CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md).  
  
 Arkadaş derlemeleri özelliğini kullanarak alternatif olarak, kullandığınız <xref:System.Security.Permissions.StrongNameIdentityPermission> tek tek türlerine erişimi kısıtlamak için.  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği:   **/CLR**  
  
### <a name="examples"></a>Örnekler  
 Aşağıdaki kod örneğinde bileşeni türlerine erişimi olan bir istemci derleme belirten bir bileşen tanımlar.  
  
```cpp  
// friend_assemblies.cpp  
// compile by using: /clr /LD  
using namespace System::Runtime::CompilerServices;  
using namespace System;  
// an assembly attribute, not bound to a type  
[assembly:InternalsVisibleTo("friend_assemblies_2")];  
  
ref class Class1 {  
public:  
   void Test_Public() {  
      Console::WriteLine("Class1::Test_Public");  
   }  
};  
```  
  
 Sonraki kod örneği, özel bir bileşen türü erişir.  
  
```cpp  
// friend_assemblies_2.cpp  
// compile by using: /clr  
#using "friend_assemblies.dll" as_friend  
  
int main() {  
   Class1 ^ a = gcnew Class1;  
   a->Test_Public();  
}  
```  
  
```Output  
Class1::Test_Public  
```  
  
 Sonraki kod örneği bir bileşen tanımlar ancak türleri bileşeni erişebilecek bir istemci derleme belirtmiyor.  
  
 Bileşen kullanarak bağlanır fark **/ opt: noref**. Bu özel türleri ne zaman gerekli değildir bileşenin meta verilerde gösterilen sağlar `InternalsVisibleTo` özniteliği varsa. Daha fazla bilgi için bkz: [OPT (iyileştirmeler)](../build/reference/opt-optimizations.md).  
  
```cpp  
// friend_assemblies_3.cpp  
// compile by using: /clr /LD /link /opt:noref  
using namespace System;  
  
ref class Class1 {  
public:  
   void Test_Public() {  
      Console::WriteLine("Class1::Test_Public");  
   }  
};  
```  
  
 Aşağıdaki kod örneğinde özel tür erişimi özel türlerinden sağlamaz bir bileşen tarafından erişmeye çalışan istemci tanımlar. Özel durum catch istiyorsanız çalışma zamanı davranışını nedeniyle, özel bir yardımcı bir işlev türü erişmeyi denemeye gerekir.  
  
```cpp  
// friend_assemblies_4.cpp  
// compile by using: /clr  
#using "friend_assemblies_3.dll" as_friend  
using namespace System;  
  
void Test() {  
   Class1 ^ a = gcnew Class1;  
}  
  
int main() {  
   // to catch this kind of exception, use a helper function  
   try {  
      Test();     
   }  
   catch(MethodAccessException ^ e) {  
      Console::WriteLine("caught an exception");  
   }  
}  
```  
  
```Output  
caught an exception  
```
  
 Sonraki kod örneği türleri bileşeni erişebilecek bir istemci derleme belirtir bir güçlü ad bileşeni oluşturulacağını gösterir.  
  
```cpp  
// friend_assemblies_5.cpp  
// compile by using: /clr /LD /link /keyfile:friend_assemblies.snk  
using namespace System::Runtime::CompilerServices;  
using namespace System;  
// an assembly attribute, not bound to a type  
  
[assembly:InternalsVisibleTo("friend_assemblies_6, PublicKey=00240000048000009400000006020000002400005253413100040000010001000bf45d77fd991f3bff0ef51af48a12d35699e04616f27ba561195a69ebd3449c345389dc9603d65be8cd1987bc7ea48bdda35ac7d57d3d82c666b7fc1a5b79836d139ef0ac8c4e715434211660f481612771a9f7059b9b742c3d8af00e01716ed4b872e6f1be0e94863eb5745224f0deaba5b137624d7049b6f2d87fba639fc5")];  
  
private ref class Class1 {  
public:  
   void Test_Public() {  
      Console::WriteLine("Class1::Test_Public");  
   }  
};  
```  
  
 Bileşen, ortak anahtarı belirtmeniz gerektiğini unutmayın. Aşağıdaki komutları sırayla bir anahtar çifti oluşturma ve ortak anahtarı almak için komut isteminde çalıştırmanızı öneririz:  
  
 **sn -d friend_assemblies.snk**  
  
 **sn -k friend_assemblies.snk**  
  
 **sn -i friend_assemblies.snk friend_assemblies.snk**  
  
 **sn -pc friend_assemblies.snk key.publickey**  
  
 **sn - tp key.publickey**  
  
 Sonraki kod örneği, bir özel tür tanımlayıcı ad bileşeninde erişir.  
  
```cpp  
// friend_assemblies_6.cpp  
// compile by using: /clr /link /keyfile:friend_assemblies.snk  
#using "friend_assemblies_5.dll" as_friend  
  
int main() {  
   Class1 ^ a = gcnew Class1;  
   a->Test_Public();  
}  
```  
  
```Output  
Class1::Test_Public  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma Zamanı Platformları için Bileşen Uzantıları](../windows/component-extensions-for-runtime-platforms.md)