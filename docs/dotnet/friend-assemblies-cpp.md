---
description: 'Daha fazla bilgi edinin: arkadaş derlemeler (C++)'
title: Arkadaş Derlemeler (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- friend assemblies, Visual C++
ms.assetid: 8d55fee0-b7c2-4fbe-a23b-dfe424dc71cd
ms.openlocfilehash: 3f5a7dcd8833d6d396acfff5f42f6c1709327b2f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97252135"
---
# <a name="friend-assemblies-c"></a>Arkadaş Derlemeler (C++)

İlgili çalışma zamanları için, *Friend derlemeleri* dil özelliği, bir derleme bileşenindeki ad alanı kapsamında veya genel kapsamda bulunan türleri bir veya daha fazla istemci derlemesine veya. netmodules erişilebilir hale getirir.

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

**Açıklamalar**

(Bu dil özelliği tüm çalışma zamanları içinde desteklenmez.)

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

**Açıklamalar**

(Bu dil özelliği Windows Çalışma Zamanı desteklenmez.)

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: **/ZW**

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

**Açıklamalar**

#### <a name="to-make-types-at-namespace-scope-or-global-scope-in-an-assembly-component-accessible-to-a-client-assembly-or-netmodule"></a>Bir istemci derlemesine veya. netmodule 'ye erişilebilen bir derleme bileşenindeki ad alanı kapsamında veya genel kapsamda tür oluşturmak için

1. Bileşeninde, bir derleme özniteliği belirtin <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> ve bileşen ad alanı kapsamında veya genel kapsamda türlere erişecek istemci derlemesinin veya. netmodule adını geçirin.  Ek öznitelikler belirterek, birden çok istemci derlemesi veya. netmodules belirtebilirsiniz.

1. İstemci derlemesinde veya. netmodule 'de, kullanarak bileşen derlemesine başvurduğunuzda `#using` , **`as_friend`** özniteliğini geçirin.  **`as_friend`** Belirtmeyen bir derlemenin özniteliğini belirtirseniz `InternalsVisibleToAttribute` , bileşendeki ad alanı kapsamında veya genel kapsamda bir türe erişmeyi denerseniz bir çalışma zamanı özel durumu oluşturulur.

Özniteliği içeren derlemenin <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> tanımlayıcı bir adı yoksa ve özniteliği kullanan istemci derlemesi ise, derleme hatası ortaya kalır **`as_friend`** .

Ad alanı kapsamı ve genel kapsamdaki türler istemci derlemesi veya. netmodule tarafından tanınabilse de, üye erişilebilirliği hala etkin olur.  Örneğin, özel bir üyeye erişemezsiniz.

Bir derlemedeki tüm türlere erişime açıkça izin verilmelidir.  Örneğin, derleme c derleme B 'ye başvuruyorsa ve derleme B, derleme A 'daki tüm türlere erişim içeriyorsa, derleme C, derleme içindeki tüm türlere erişemez.

Nasıl oturum yapılacağı hakkında bilgi için, yani Microsoft C++ derleyicisi kullanılarak oluşturulan bir derleme olan güçlü bir ad verme hakkında bilgi için bkz. [tanımlayıcı ad derlemeleri (derleme imzalama) (C++/CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md).

Arkadaş derlemeleri özelliğinin kullanımına alternatif olarak, <xref:System.Security.Permissions.StrongNameIdentityPermission> tek tek türlere erişimi kısıtlamak için kullanabilirsiniz.

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: **/clr**

### <a name="examples"></a>Örnekler

Aşağıdaki kod örneği, bileşen içindeki türlere erişimi olan bir istemci derlemesini belirten bir bileşeni tanımlar.

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

Sonraki kod örneği, bileşendeki özel bir türe erişir.

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

Sonraki kod örneği bir bileşeni tanımlar, ancak bileşendeki türlere erişimi olacak bir istemci derlemesini belirtmez.

Bileşenin **/OPT: NOREF** kullanılarak bağlı olduğuna dikkat edin. Bu, özel türlerin bileşen meta verilerinde yayılmasını sağlar, bu öznitelik mevcut olduğunda gerekli değildir `InternalsVisibleTo` . Daha fazla bilgi için bkz. [/opt (iyileştirmeler)](../build/reference/opt-optimizations.md).

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

Aşağıdaki kod örneği, özel türlerine erişim izni verilmeyen bir bileşende özel bir türe erişmeye çalışan bir istemciyi tanımlar. Çalışma zamanının davranışı nedeniyle özel durumu yakalamak istiyorsanız, bir yardımcı işlevinde özel bir türe erişmeyi denemeniz gerekir.

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

Sonraki kod örneğinde, bileşendeki türlere erişimi olacak bir istemci derlemesini belirten bir tanımlayıcı ad bileşeninin nasıl oluşturulacağı gösterilmektedir.

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

Bileşenin ortak anahtarını belirtmesi gerektiğini unutmayın. Anahtar çifti oluşturmak ve ortak anahtarı almak için komut isteminde aşağıdaki komutları sırayla çalıştırmanızı öneririz:

**sn-d friend_assemblies. snk**

**sn-k friend_assemblies. snk**

**sn-i friend_assemblies. snk friend_assemblies. snk**

**sn-PC friend_assemblies. snk Key. PublicKey**

**sn-TP Key. PublicKey**

Sonraki kod örneği, Strong-Name bileşenindeki özel bir türe erişir.

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

## <a name="see-also"></a>Ayrıca bkz.

[Çalışma Zamanı Platformları için Bileşen Uzantıları](../extensions/component-extensions-for-runtime-platforms.md)
