---
title: EXPORTS
ms.date: 09/07/2018
f1_keywords:
- EXPORTS
helpviewer_keywords:
- EXPORTS .def file statement
ms.assetid: dbcd7579-b855-44c4-bd27-931e157657f7
ms.openlocfilehash: 9ede0d3b53c975298dea3d1331bc0fb00ac246b2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328252"
---
# <a name="exports"></a>EXPORTS

Dışa aktarılan adları veya işlevveya verilerin konumlarını belirten bir veya daha fazla dışa aktarma tanımının bir bölümünü tanır. Her tanım ayrı bir satırda olmalıdır.

```DEF
EXPORTS
   definition
```

## <a name="remarks"></a>Açıklamalar

İlk `EXPORTS` *tanım,* anahtar kelimeyle aynı satırda veya sonraki bir satırda olabilir. Şey. DEF dosyası bir veya `EXPORTS` daha fazla deyim içerebilir.

Bir dışa aktarma *tanımı* için sözdizimi:

> *entryname*\[__=__*internal_name*|*other_module.exported_name*] \[ **\@** _ordinal_ \[ **NONAME**] \[ \[ **ÖZEL**] | \[ **VERI**] ]

*entryname,* dışa aktarmak istediğiniz işlev veya değişken adıdır. Bu gereklidir. Dışa aktardığınız ad DLL'deki addan farklıysa, *internal_name*kullanarak Dışa aktarAn ın adını DLL'de belirtin. Örneğin, DLL'niz bir `func1` işlev dışa ysa ve `func2`arayanların bu işlevi "olarak" olarak kullanmasını istiyorsanız şunları belirtirsiniz:

```DEF
EXPORTS
   func2=func1
```

Dışa aktardığınız ad başka bir modülden geliyorsa, *other_module,exported_name*kullanarak DLL'deki dışa aktarmanın adını belirtin. Örneğin, DLL'niz bir `other_module.func1` işlev dışa ysa ve `func2`arayanların bu işlevi "olarak" olarak kullanmasını istiyorsanız şunları belirtirsiniz:

```DEF
EXPORTS
   func2=other_module.func1
```

Dışa aktardığınız ad, ordinal tarafından dışa aktaran başka bir modülden geliyorsa, *other_module*kullanarak DLL'deki ihracat ordinalını belirtin. __#__ *ordinal*. Örneğin, DLL'niz bir işlevi 42 no'lu diğer modülden dışa ysa ve arayanların `func2`bu işlevi kullanarak kullanmasını istiyorsanız, şunları belirtirsiniz:

```DEF
EXPORTS
   func2=other_module.#42
```

MSVC derleyicisi C++ işlevleri için ad dekorasyonu kullandığından, süslü adı *internal_name* `extern "C"` kullanmanız veya kaynak kodunda kullanarak dışa aktarılan işlevleri tanımlamanız gerekir. Derleyici [ayrıca, __stdcall](../../cpp/stdcall.md) çağrı kuralını alt\_() öneki ve at işaretinden oluşan bir sonek (\@) ve ardından bağımsız değişken listesindeki bayt (ondalık) sayısını içeren C işlevlerini de süsler.

Derleyici tarafından üretilen dekore edilmiş adları bulmak için [DUMPBIN](dumpbin-reference.md) aracını veya bağlayıcı [/MAP](map-generate-mapfile.md) seçeneğini kullanın. Dekore edilmiş adlar derleyiciye özgüdir. Eğer dekore edilmiş adları dışa aktarın. DEF dosyası, DLL'ye bağlanan yürütülebilir ler de derleyicinin aynı sürümü kullanılarak oluşturulmalıdır. Bu, arayandaki dekore edilmiş adların dışa aktarılan adlarla eşleşmesini sağlar. DEF dosyası.

İşlev \@adının değil, bir sayının DLL'nin dışa aktarma tablosuna girdiğini belirtmek için *ordinal'ı* kullanabilirsiniz. Birçok Windows DLs eski kodu desteklemek için ordinals dışa aktarıyor. Bir DLL boyutunu en aza indirmeye yardımcı olabilir, çünkü 16-bit Windows kodunda ordinals kullanmak için yaygın dı. DLL istemcileriniz eski destek için ihtiyaç dolmadığı sürece, işlevleri ordinal ile dışa aktarmayı önermiyoruz. Çünkü. LIB dosyası ordinal ve işlev arasında eşleme içerecektir, dll kullanan projelerde normalde olduğu gibi işlev adını kullanabilirsiniz.

İsteğe bağlı **NONAME** anahtar sözcük kullanarak, yalnızca ordinal ile dışa aktarabilir ve ortaya çıkan DLL'deki dışa aktarma tablosunun boyutunu küçültebilirsiniz. Ancak, DLL'de [GetProcAddress](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress) kullanmak istiyorsanız, ad geçerli olmayacaktır, çünkü ordinal bilmeniz gerekir.

İsteğe bağlı PRIVATE **anahtar** *kelimesi, giriş adının* LINK tarafından oluşturulan alma kitaplığına eklenmesini engeller. LINK tarafından oluşturulan görüntüdeki dışa aktarmayı etkilemez.

İsteğe bağlı anahtar kelime **DATA,** dışa aktarmanın kod değil veri olduğunu belirtir. Bu örnek, adlı bir veri `exported_global`değişkenini nasıl dışa aktarabileceğinizi gösterir:

```DEF
EXPORTS
   exported_global DATA
```

Önerilen sırada listelenen bir tanımı dışa aktarmanın dört yolu vardır:

1. Kaynak kodundaki [__declspec(dllexport)](../../cpp/dllexport-dllimport.md) anahtar sözcüğü

1. Bir `EXPORTS` ifade . DEF dosyası

1. LINK komutundaki [/EXPORT](export-exports-a-function.md) belirtimi

1. Formun `#pragma comment(linker, "/export: definition ")`kaynak kodunda bir [açıklama](../../preprocessor/comment-c-cpp.md) yönergesi. Aşağıdaki örnek, işlev bildiriminden önce #pragma `PlainFuncName` bir açıklama yönergesi `_PlainFuncName@4` gösterir, dekore edilmemiş adın yeri dir ve işlevin dekore edilmiş adıdır:

    ```cpp
    #pragma comment(linker, "/export:PlainFuncName=_PlainFuncName@4")
    BOOL CALLBACK PlainFuncName( Things * lpParams)
    ```

#pragma yönergesi, dekore edilmemiş bir işlev adı dışa aktarmanız gerekiyorsa ve yapı yapılandırmasına bağlı olarak (örneğin, 32 bit veya 64 bit yapılarda) farklı dışa aktarmanız gerekiyorsa yararlıdır.

Dört yöntem de aynı programda kullanılabilir. LINK dışa aktarma içeren bir program oluşturduğunda, bir . EXP dosyası yapıda kullanılır.

İşte Bir İhRACAT bölümüne bir örnek:

```DEF
EXPORTS
   DllCanUnloadNow      @1          PRIVATE
   DllWindowName = WindowName       DATA
   DllGetClassObject    @4 NONAME   PRIVATE
   DllRegisterServer    @7
   DllUnregisterServer
```

Bir DLL'den bir değişkeni kullanarak dışa aktardığınızda. DEF dosyası, değişken üzerinde `__declspec(dllexport)` belirtmeniz gerekmez. Ancak, DLL kullanan herhangi bir dosyada, `__declspec(dllimport)` yine de veri bildirimini kullanmanız gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Modül Tanımlama Deyimleri Kuralları](rules-for-module-definition-statements.md)
