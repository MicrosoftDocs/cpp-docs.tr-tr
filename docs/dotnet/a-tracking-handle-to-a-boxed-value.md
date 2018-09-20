---
title: Paketlenmiş değere izleme işleyicisi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- boxed value types, tracking handle to
ms.assetid: 16c92048-5b74-47d5-8eca-dfea3d38879a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c7e26efae93b509700c3bb0c992d9f397559e99f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46380740"
---
# <a name="a-tracking-handle-to-a-boxed-value"></a>Paketlenmiş Değere İzleme İşleyicisi

Değer türüne başvuru izleme işleyicisi kullanımını, C++ için Visual C++ için Yönetilen Uzantılar'dan değişti.

Kutulama bir yaný birleşik CLR tür sistemi ' dir. Değer türleri başvuru türleri örtülü olsa da, durumlarını doğrudan içerir: yönetilen yığında ayrılan adlandırılmamış bir nesne için bir tanıtıcı, adlandırılmış varlık olduğu. Herhangi bir değer atama için yazın veya başlatma bir `Object`, örneğin, değer türü - bu, burada, kutulama görüntüsü ortaya - CLR yığınına yerleştirilmesini önce ilişkili bellek ayırma sonra değer türün durumunun kopyalama gerektirir ve ardından bu anonim referans/karma adresini döndürüyor. Bu nedenle, bir C# dilinde yazdığında

```cpp
object o = 1024; // C# implicit boxing
```

kod basitliğinin tarafından görünür yapılan daha çok daha geçmeden yoktur. C# tasarımını yalnızca hangi işlemleri başlık altında yer alan, ancak soyutlama kutulamanın kendi karmaşıklığını gizler. Yönetilen c++, diğer taraftan, uzantılar bu verimlilik için yanlış bir fikir sunulmasını, açık bir yönerge gerektirerek kullanıcının yüzdeki koyar ilgili:

```cpp
Object *o = __box( 1024 ); // Managed Extensions explicit boxing
```

Visual c++'ta örtük kutulama:

```cpp
Object ^o = 1024; // new syntax implicit boxing
```

`__box` Anahtar sözcüğü çok önemli bir hizmet içinde Yönetilen Uzantılar, eksik bir hizmet tarafından C# ve Visual Basic gibi dillerden gelen tasarım: işlemek yönetilen yığındaki paketlenmiş bir örneği doğrudan işlemek için bir sözlük ve izleme sağlar. Örneğin, aşağıdaki küçük program göz önünde bulundurun:

```cpp
int main() {
   double result = 3.14159;
   __box double * br = __box( result );

   result = 2.7;
   *br = 2.17;
   Object * o = br;

   Console::WriteLine( S"result :: {0}", result.ToString() ) ;
   Console::WriteLine( S"result :: {0}", __box(result) ) ;
   Console::WriteLine( S"result :: {0}", br );
}
```

Üç çağrıları için oluşturulan arka plandaki kod `WriteLine` kutulanmış değer değerini erişmenin çeşitli maliyetleri yazın (Yves bu farklılıkları işaret eden için değerine sayesinde), burada gösterilen satırlar her ile ilgili ek yükü Göster Göster çağırma.

```cpp
// Console::WriteLine( S"result :: {0}", result.ToString() ) ;
ldstr      "result :: {0}"
ldloca.s   result  // ToString overhead
call       instance string  [mscorlib]System.Double::ToString()  // ToString overhead
call       void [mscorlib]System.Console::WriteLine(string, object)

// Console::WriteLine( S"result :: {0}", __box(result) ) ;
Ldstr    " result :: {0}"
ldloc.0
box    [mscorlib]System.Double // box overhead
call    void [mscorlib]System.Console::WriteLine(string, object)

// Console::WriteLine( S"result :: {0}", br );
ldstr    "result :: {0}"
ldloc.0
call     void [mscorlib]System.Console::WriteLine(string, object)
```

Paketlenmiş değer türü doğrudan geçirme `Console::WriteLine` hem kutulama hem de çağırma ihtiyacını ortadan kaldıran `ToString()`. (Kuşkusuz, başlatmak için önceki kutulama yoktur `br`, gerçekten put sürece her şeyi elde yoksa `br` çalışmak için.

Yeni sözdiziminde, paketlenmiş değer türleri için destek gücünü korurken önemli ölçüde daha şık ve tür sistemine tümleşiktir. Örneğin, küçük bir önceki program çevirisi şu şekildedir:

```cpp
int main()
{
   double result = 3.14159;
   double^ br = result;
   result = 2.7;
   *br = 2.17;
   Object^ o = br;
   Console::WriteLine( "result :: {0}", result.ToString() );
   Console::WriteLine( "result :: {0}", result );
   Console::WriteLine( "result :: {0}", br );
}
```

## <a name="see-also"></a>Ayrıca Bkz.

[Değer Türleri ve Davranışları (C++/CLI)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)<br/>
[Nasıl yapılır: Açık Şekilde İstek Paketleme](../dotnet/how-to-explicitly-request-boxing.md)