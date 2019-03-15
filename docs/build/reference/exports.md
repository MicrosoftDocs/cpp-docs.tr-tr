---
title: EXPORTS
ms.date: 09/07/2018
f1_keywords:
- EXPORTS
helpviewer_keywords:
- EXPORTS .def file statement
ms.assetid: dbcd7579-b855-44c4-bd27-931e157657f7
ms.openlocfilehash: 33b70c680bfc3db24f5326a2027fa9ec4740e3f2
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57814143"
---
# <a name="exports"></a>EXPORTS

Dışa aktarılan adlarla belirten bir veya daha fazla dışarı aktarma tanımları bir bölümünü veya sıra sayıları işlevleri veya verileri ortaya çıkarır. Her tanım ayrı bir satırda olmalıdır.

```DEF
EXPORTS
   definition
```

## <a name="remarks"></a>Açıklamalar

İlk *tanımı* aynı satırda olabilir `EXPORTS` anahtar sözcüğü veya bir sonraki satırda. . DEF dosyası, bir veya daha fazla içerebilir `EXPORTS` deyimleri.

Bir dışarı aktarma için söz dizimi *tanımı* olan:

> *entryname*\[__=__*internal_name*|*other_module.exported_name*] \[**\@**_ordinal_ \[**NONAME**] ] \[ \[**PRIVATE**] | \[**DATA**] ]

*GirişAdı* dışarı aktarmak istediğiniz işlev veya değişken adı. Bu gereklidir. Dll adı vermek istediğiniz adı farklıysa, dışarı aktarma'nın adı DLL'deki kullanarak belirtin *internal_name*. Örneğin, bir işlev, DLL dışarı aktarmaları `func1` ve çağrı yapanların olarak kullanmak istediğiniz `func2`, şunu belirtmeniz gerekir:

```DEF
EXPORTS
   func2=func1
```

Diğer bazı modülünden dışarı adı ise dışarı aktarma'nın adı DLL'deki kullanarak belirtin *other_module.exported_name*. Örneğin, bir işlev, DLL dışarı aktarmaları `other_module.func1` ve çağrı yapanların olarak kullanmak istediğiniz `func2`, şunu belirtmeniz gerekir:

```DEF
EXPORTS
   func2=other_module.func1
```

Dışarı aktarma DLL'de sıralı kullanarak dışarı aktarmak istediğiniz adı, sıralı olarak dışarı aktarır, başka bir modülden ise belirtin *other_module*.__#__ *sıralı*. Örneğin, burada, sıralı 42 ve çağrı yapanların olarak kullanmak istediğiniz diğer modülünde DLL'niz işlevi dışarı aktarır `func2`, şunu belirtmeniz gerekir:

```DEF
EXPORTS
   func2=other_module.#42
```

MSVC derleyicisi için C++ işlevlerini bir düzenlemeyi Adlandır kullandığından, ya da düzenlenmiş adı kullanmalıdır *internal_name* veya dışarı aktarılan işlevleri kullanarak tanımladığınız `extern "C"` kaynak kodunda. Derleyici kullanmak için C işlevlerini de düzenler [__stdcall](../../cpp/stdcall.md) çağırma kuralı ile bir alt çizgi (\_) önek ve sonek oluşan at işareti (\@) (ondalık) bayt sayısı, ardından bağımsız değişken listesi.

Derleyici tarafından üretilen düzenlenmiş adların bulmak için kullanın [DUMPBIN](dumpbin-reference.md) aracını veya bağlayıcı [/MAP](map-generate-mapfile.md) seçeneği. Düzenlenmiş adlar derleyici özgüdür. Düzenlenmiş adları dışa aktarmak istemiyorsanız. DEF dosyası için DLL'e yürütülebilir dosyalar derleyici aynı sürümünü kullanarak da oluşturulmalıdır. Bu çağrıyı düzenlenmiş adları dışarı aktarılan adlarının eşleştiğini sağlar. DEF dosyası.

Kullanabileceğiniz \@ *sıralı* bir sayı ve işlev adı değil, DLL'nin dışarı aktarma tablosuna giden belirtmek için. Birçok Windows DLL'leri, eski kodu desteklemek için sıra sayıları dışarı aktarın. Bir DLL boyutunu en aza indirmenize yardımcı çünkü 16-bit Windows kod içinde sıra sayıları kullanmak yaygın. İsteğe bağlı olarak, DLL'nin istemci için eski destek gerekli olmadıkça işlevlerini dışa aktarma sıra sayısı ile önerilmemektedir. Çünkü. LIB dosyası sıra ile işlevi arasındaki eşlemeyi içerir, DLL kullanan projelerde normalde yaptığınız gibi işlev adı kullanabilirsiniz.

İsteğe bağlı kullanarak **NONAME** anahtar sözcüğü, yalnızca sıralı olarak dışarı aktarma ve ortaya çıkan DLL'yi dışa aktarma tablosunda boyutunu küçültün. Ancak, kullanmak istiyorsanız [GetProcAddress](/windows/desktop/api/libloaderapi/nf-libloaderapi-getprocaddress) DLL adı geçerli değil çünkü sıra bilmeniz gerekir.

İsteğe bağlı anahtar sözcük **özel** engeller *GirişAdı* bağlantı tarafından oluşturulan içeri aktarma kitaplığına eklenen öğesinden. Dışa aktarma, ayrıca bağlantı tarafından oluşturulan görüntüyü etkilemez.

İsteğe bağlı anahtar sözcük **veri** verme kod değil veri olduğunu belirtir. Bu örnek adlı bir veri değişkeni nasıl dışarı aktarılamadı gösterir `exported_global`:

```DEF
EXPORTS
   exported_global DATA
```

Önerilen sırayla yeniden listelenmiş bir tanımını dışarı aktarma için izleyebileceğiniz dört yol vardır:

1. [__Declspec(dllexport)](../../cpp/dllexport-dllimport.md) kaynak koddaki anahtar sözcüğü

1. Bir `EXPORTS` deyiminde bir. DEF dosyası

1. Bir [/dışarı aktarma](export-exports-a-function.md) bağlantı komut belirtimi

1. A [yorum](../../preprocessor/comment-c-cpp.md) yönergesi, kaynak kodda, formun `#pragma comment(linker, "/export: definition ")`. Aşağıdaki örnek, bir işlev bildiriminden önce #pragma comment yönergesi gösterir. burada `PlainFuncName` ve adıdır ve `_PlainFuncName@4` işlev düzenlenmiş adı:

    ```cpp
    #pragma comment(linker, "/export:PlainFuncName=_PlainFuncName@4")
    BOOL CALLBACK PlainFuncName( Things * lpParams)
    ```

#Pragma yönergesi ve işlev adı dışarı aktarma ve derleme yapılandırmasına bağlı olarak farklı verir (örneğin, 32 bit veya 64 bit derlemelerde) sahip gerektiğinde kullanışlıdır.

Tüm dört yöntemi, aynı programda kullanılabilir. BAĞLANTI dışarı aktarmaları içeren bir program oluşturduğunda, ayrıca bir içeri aktarma kitaplığını sürece oluşturur bir. EXP dosyası derlemede kullanılır.

Dışarı aktarmalar bölümün bir örnek aşağıda verilmiştir:

```DEF
EXPORTS
   DllCanUnloadNow      @1          PRIVATE
   DllWindowName = WindowName       DATA
   DllGetClassObject    @4 NONAME   PRIVATE
   DllRegisterServer    @7
   DllUnregisterServer
```

Dışarı aktardığınızda bir değişken DLL'den kullanarak bir. DEF dosyası sahip olmadığınız belirtmek `__declspec(dllexport)` değişken. Ancak, DLL kullanan herhangi bir dosyayı, yine de kullanmalısınız `__declspec(dllimport)` bildiriminde veri.

## <a name="see-also"></a>Ayrıca bkz.

[Modül Tanımlama Deyimleri Kuralları](rules-for-module-definition-statements.md)
