---
description: 'Daha fazla bilgi edinin: dışarı aktarmalar'
title: EXPORTS
ms.date: 09/07/2018
f1_keywords:
- EXPORTS
helpviewer_keywords:
- EXPORTS .def file statement
ms.assetid: dbcd7579-b855-44c4-bd27-931e157657f7
ms.openlocfilehash: b886f626854012c3cc477fcb11ac74a1e7776299
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192355"
---
# <a name="exports"></a>EXPORTS

Dışarı aktarılmış adları veya işlev ya da veri sıra sayılarını belirten bir veya daha fazla dışa aktarma tanımının bir bölümünü tanıtır. Her tanım ayrı bir satırda olmalıdır.

```DEF
EXPORTS
   definition
```

## <a name="remarks"></a>Açıklamalar

İlk *tanım* , `EXPORTS` anahtar sözcüğüyle veya sonraki bir satırda aynı satırda olabilir. İçin. DEF dosyası bir veya daha fazla `EXPORTS` deyim içerebilir.

Dışarı aktarma *tanımının* sözdizimi şöyledir:

>  \[ EntryName __=__ *internal_name* | *other_module.exported_name*] \[ **\@** _sıralı_ \[ **noname**] \[ ] \[ **Özel**] | \[ **Veri**]]

*EntryName* , dışarı aktarmak istediğiniz işlev veya değişken adıdır. Bu gereklidir. Dışarı aktarma işlemi yaptığınız ad DLL 'deki addan farklıysa, *internal_name* kullanarak dll 'de dışarı aktarma adını belirtin. Örneğin, DLL 'niz bir işlevi dışarı `func1` aktarırın ve arayanların bunu olarak kullanmasını istiyorsanız `func2` şunu belirtin:

```DEF
EXPORTS
   func2=func1
```

Dışarı aktarma yaptığınız ad başka bir modülden ise, *other_module. exported_name* kullanarak dll 'de dışarı aktarma adını belirtin. Örneğin, DLL 'niz bir işlevi dışarı `other_module.func1` aktarırın ve arayanların bunu olarak kullanmasını istiyorsanız `func2` şunu belirtin:

```DEF
EXPORTS
   func2=other_module.func1
```

Dışa aktarma yaptığınız ad, sıra tarafından dışarı aktarılan başka bir modülden ise, *other_module* kullanarak dll 'de dışarı aktarmanın sıra sayısını belirtin. __#__ *sıra sayısı*. Örneğin, DLL 'niz, diğer modülden 42 sıra olan bir işlevi dışarı aktardığında ve çağıranların bunu olarak kullanmasını istiyorsanız şunları `func2` belirtmeniz gerekir:

```DEF
EXPORTS
   func2=other_module.#42
```

MSVC derleyicisi C++ işlevleri için ad dekorasyonu kullandığından, düzenlenmiş adı kullanmanız veya kaynak kodunda ' ı kullanarak içe aktarılmış işlevleri tanımlamanız *internal_name* gerekir `extern "C"` . Derleyici Ayrıca, bir alt çizgi () önekiyle [__stdcall](../../cpp/stdcall.md) çağırma kuralını kullanan C işlevlerini ve @ \_ işareti () ile birlikte \@ bağımsız değişken listesindeki bayt sayısı (ondalık olarak) içeren bir sonek de tasarlayarak.

Derleyici tarafından üretilen düzenlenmiş adları bulmak için, [dumpbin](dumpbin-reference.md) aracını veya bağlayıcı [/map](map-generate-mapfile.md) seçeneğini kullanın. Düzenlenmiş adlar derleyiciye özgüdür. İçinde düzenlenmiş adları dışarı aktardıysanız. DEF dosyası, DLL 'ye bağlanan yürütülebilir dosyaların aynı derleyici sürümü kullanılarak da oluşturulması gerekir. Bu, çağırandaki düzenlenmiş adların içindeki ' de bulunan adlarla eşleşmesini sağlar. DEF dosyası.

\@ *Sıra* sayısını, işlev adı değil, dll 'nin dışarı aktarma tablosuna gidebilmeniz için kullanabilirsiniz. Birçok Windows dll, eski kodu desteklemek için sıra sayılarını dışarı aktarır. 16 bit Windows kodunda sıra sayıları kullanılması yaygındır, çünkü DLL boyutunu en aza indirmenize yardımcı olabilir. DLL 'nizin istemcileri eski destek için ihtiyaç duymadığı takdirde, işlevleri sıraya göre dışarı aktarmayı önermiyoruz. Çünkü. LıB dosyası, Ordinal ve işlevi arasındaki eşlemeyi içerecektir, işlev adını normalde DLL kullanan projelerde yaptığınız gibi kullanabilirsiniz.

İsteğe bağlı **noname** anahtar sözcüğünü kullanarak yalnızca sıra sayısına göre dışa aktarabilir ve elde edilen dll 'deki dışa aktarma tablosunun boyutunu azaltabilirsiniz. Ancak, DLL üzerinde [GetProcAddress](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress) kullanmak istiyorsanız, ad geçerli olmayacak şekilde sıra sayısını bilmeniz gerekir.

İsteğe bağlı anahtar sözcük **özel** anahtar *EntryName* , bağlantı tarafından oluşturulan içeri aktarma kitaplığına dahil edilmesini engeller. Aynı zamanda bağlantı tarafından oluşturulan görüntüde dışarı aktarmayı etkilemez.

İsteğe bağlı anahtar sözcük **verileri** , dışa aktarma kodunun değil, veri olduğunu belirtir. Bu örnekte adlı bir veri değişkenini nasıl dışarı aktarabilirsiniz gösterilmektedir `exported_global` :

```DEF
EXPORTS
   exported_global DATA
```

Bir tanımı dışa aktarmanın önerilen sırada listelenen dört yolu vardır:

1. Kaynak kodundaki [__declspec (dllexport)](../../cpp/dllexport-dllimport.md) anahtar sözcüğü

1. `EXPORTS`İçindeki bir ifade. DEF dosyası

1. BAĞLANTı komutunda bir [/Export](export-exports-a-function.md) belirtimi

1. Formun kaynak kodunda bir [Açıklama](../../preprocessor/comment-c-cpp.md) yönergesi `#pragma comment(linker, "/export: definition ")` . Aşağıdaki örnek, bir işlev bildiriminden önce bir #pragma yorumu yönergesini gösterir, burada `PlainFuncName` açıklanmamış ad ve `_PlainFuncName@4` işlevin düzenlenmiş adıdır:

    ```cpp
    #pragma comment(linker, "/export:PlainFuncName=_PlainFuncName@4")
    BOOL CALLBACK PlainFuncName( Things * lpParams)
    ```

#Pragma yönergesi, desteklenmeyen bir işlev adını dışa aktarmanız ve derleme yapılandırmasına bağlı olarak farklı dışarı aktarmalar (örneğin, 32-bit veya 64 bit derlemeler) varsa yararlıdır.

Dört yöntem de aynı programda kullanılabilir. BAĞLANTı, dışarı aktarmalar içeren bir program oluşturduğunda, bir içeri aktarma kitaplığı da oluşturur. EXP dosyası derlemede kullanılıyor.

Dışarı aktarmalar bölümüne bir örnek aşağıda verilmiştir:

```DEF
EXPORTS
   DllCanUnloadNow      @1          PRIVATE
   DllWindowName = WindowName       DATA
   DllGetClassObject    @4 NONAME   PRIVATE
   DllRegisterServer    @7
   DllUnregisterServer
```

Kullanarak bir değişkeni bir DLL 'den dışarı aktardığınızda. DEF dosyası, değişkende belirtmeniz gerekmez `__declspec(dllexport)` . Ancak, DLL 'yi kullanan herhangi bir dosyada, hala veri bildiriminde kullanmanız gerekir `__declspec(dllimport)` .

## <a name="see-also"></a>Ayrıca bkz.

[Module-Definition deyimleri için kurallar](rules-for-module-definition-statements.md)
