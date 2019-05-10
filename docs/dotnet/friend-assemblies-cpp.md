---
title: Arkadaş Derlemeler (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- friend assemblies, Visual C++
ms.assetid: 8d55fee0-b7c2-4fbe-a23b-dfe424dc71cd
ms.openlocfilehash: 05b9d8bcf5d7364e1dcd31940bc0db64a5e605f1
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447310"
---
# <a name="friend-assemblies-c"></a>Arkadaş Derlemeler (C++)

Geçerli çalışma zamanları için *arkadaş bütünleştirilmiş kodları* ad alanı kapsamında ya da bir veya daha fazla istemci derlemelerine veya netmodule'leri erişilebilir bir derleme bileşeninin genel kapsamda türlere dil özelliği sağlar.

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

**Açıklamalar**

(Bu dil özelliği tüm çalışma zamanları desteklenmiyor.)

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

**Açıklamalar**

(Bu dil özelliği, Windows çalışma zamanı'nda desteklenmiyor.)

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: **/ZW**

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

**Açıklamalar**

#### <a name="to-make-types-at-namespace-scope-or-global-scope-in-an-assembly-component-accessible-to-a-client-assembly-or-netmodule"></a>Ad alanı kapsamında veya genel kapsamlı türlerini bir derleme bileşeni bir istemci bütünleştirilmiş kodu veya .netmodule erişilebilir hale getirmek için

1. Bileşeninde bir derleme özniteliğini belirtin <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>ve istemci bütünleştirilmiş kodu veya ad alanı kapsamında veya bileşen genel kapsamda türlerini erişecek .netmodule adını geçirin.  Ek öznitelikleri belirterek, birden çok istemci derlemelerine veya netmodule'leri belirtebilirsiniz.

1. İstemci derleme veya bileşen derlemesi kullanarak başvurduğunuzda .netmodule `#using`, geçmesi `as_friend` özniteliği.  Belirtirseniz `as_friend` belirttiğinde bir derleme için öznitelik `InternalsVisibleToAttribute`, ad alanı kapsamında veya genel kapsamında bileşenindeki bir tür erişmeye çalışırsanız bir çalışma zamanı özel durum oluşturulur.

Bütünleştirilmiş kod içeren bir yapı hatasına neden olur <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> özniteliği, ancak kullanan istemci derleme tanımlayıcı bir ada sahip değil `as_friend` öznitelik yapar.

Ad alanı kapsamında ve genel kapsam türleri için bir istemci bütünleştirilmiş kodu veya .netmodule bilinen olsa da, üye erişilebilirliği hala etkin olan.  Örneğin, bir özel üye erişemez.

Derlemedeki tüm türleri erişimi açıkça verilmesi gerekir.  Örneğin, derleme C erişimi tüm türleri için bir derlemede derleme B derleme C başvuruyor ve B derleme A'ya derlemede tüm türleri erişimi yok

Oturum açma hakkında bilgi — diğer bir deyişle, güçlü bir ad vermek nasıl — Microsoft kullanılarak oluşturulmuş bir derleme C++ derleyici, bakın [tanımlayıcı ad derlemeleri (derleme imzalama) (C++/CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md).

Arkadaş derlemeleri özelliğini kullanarak alternatif olarak, kullandığınız <xref:System.Security.Permissions.StrongNameIdentityPermission> tek tek türleri için erişimi kısıtlamak için.

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği:   **/CLR**

### <a name="examples"></a>Örnekler

Aşağıdaki kod örneği, bileşen türlerine erişimi olan bir istemci bütünleştirilmiş kodu belirten bir bileşeni tanımlar.

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

Sonraki kod örneğinde, bir özel tür bileşende erişir.

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

Sonraki kod örneğinde bir bileşeni tanımlar ancak bileşen türlerine erişimi olacak bir istemci bütünleştirilmiş kodu belirtmez.

Bileşeni kullanarak bağlandığını fark **/ opt: noref**. Bu özel türleri ne zaman gerekli değildir bileşenin meta verilerde gönderilir sağlar `InternalsVisibleTo` özniteliği. Daha fazla bilgi için [OPT (iyileştirmeler)](../build/reference/opt-optimizations.md).

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

Aşağıdaki kod örneği, özel bir tür özel türlerinden erişimlerini değil bir bileşende erişmeye çalışan istemci tanımlar. Özel durum yakalamak istiyorsanız çalışma zamanı davranışı nedeniyle bir yardımcı işlev özel bir tür erişme girişiminde bulunuldu gerekir.

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

Sonraki kod örneğinde, bileşen türlerine erişimi olacak bir istemci bütünleştirilmiş kodu belirten bir tanımlayıcı ad bileşen oluşturma işlemini gösterir.

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

Bileşen kendi ortak anahtar belirtmeniz gerektiğini unutmayın. Aşağıdaki komutları sırayla bir anahtar çifti oluşturma ve ortak anahtarı almak için bir komut isteminde çalıştırmanızı öneririz:

**-d friend_assemblies.snk sn**

**-k friend_assemblies.snk sn**

**sn -i friend_assemblies.snk friend_assemblies.snk**

**sn -pc friend_assemblies.snk key.publickey**

**sn - tp key.publickey**

Sonraki kod örneğinde, bir özel tür tanımlayıcı ad bileşende erişir.

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
