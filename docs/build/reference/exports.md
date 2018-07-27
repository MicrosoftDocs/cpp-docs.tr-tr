---
title: DIŞARI AKTARMALAR | Microsoft Docs
ms.custom: ''
ms.date: 07/11/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- EXPORTS
dev_langs:
- C++
helpviewer_keywords:
- EXPORTS .def file statement
ms.assetid: dbcd7579-b855-44c4-bd27-931e157657f7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c642a623e76a9e1344a90efd4f0a47ad195c553e
ms.sourcegitcommit: e5792fcb89b9ba64c401f90f4f26a8e45d4a2359
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2018
ms.locfileid: "39322195"
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
  
```DEF
entryname[=internal_name|other_module.another_exported_name] [@Ordinal [NONAME]] [[PRIVATE] | [DATA]]
```

*GirişAdı* dışarı aktarmak istediğiniz işlev veya değişken adı. Bu gereklidir. Dll adı vermek istediğiniz adı farklıysa, dışarı aktarma'nın adı DLL'deki kullanarak belirtin *internal_name*. Örneğin, bir işlev, DLL dışarı aktarmaları `func1` ve çağrı yapanların olarak kullanmak istediğiniz `func2`, şunu belirtmeniz gerekir:

```DEF
EXPORTS
   func2=func1
```

Başka bir modül vermek istediğiniz adı ise dışarı aktarma'nın adı DLL'deki kullanarak belirtin *other_module.exported_name*. Örneğin, bir işlev, DLL dışarı aktarmaları `other_module.func1` ve çağrı yapanların olarak kullanmak istediğiniz `func2`, şunu belirtmeniz gerekir:

```DEF
EXPORTS
   func2=other_module.func1
```

Visual C++ derleyicisi için C++ işlevlerini bir düzenlemeyi Adlandır kullandığından, düzenlenmiş adı internal_name kullanın veya extern "C" kaynak kodunda kullanarak dışarı aktarılan işlevleri tanımlar. Derleyici kullanmak için C işlevlerini de düzenler [__stdcall](../../cpp/stdcall.md) çağırma kuralı ile bir alt çizgi (_) öneki ve soneki oluşan at işareti (@) bağımsız değişken listesinde (ondalık) bayt sayısı ardından.  
  
Derleyici tarafından üretilen düzenlenmiş adların bulmak için kullanın [DUMPBIN](../../build/reference/dumpbin-reference.md) aracını veya bağlayıcı [/MAP](../../build/reference/map-generate-mapfile.md) seçeneği. Düzenlenmiş adlar derleyici özgüdür. Düzenlenmiş adları dışa aktarmak istemiyorsanız. DEF dosyası için DLL'e yürütülebilir dosyalar derleyici aynı sürümünü kullanarak da oluşturulmalıdır. Bu çağrıyı düzenlenmiş adları dışarı aktarılan adlarının eşleştiğini sağlar. DEF dosyası.  
  
Kullanabilirsiniz*sıralı* bir sayı ve işlev adı değil, DLL'nin dışarı aktarma tablosuna gideceğini belirtmek için. Birçok Windows DLL'leri, eski kodu desteklemek için sıra sayıları dışarı aktarın. Bir DLL boyutunu en aza indirmenize yardımcı çünkü 16-bit Windows kod içinde sıra sayıları kullanmak yaygın. İsteğe bağlı olarak, DLL'nin istemci için eski destek gerekli olmadıkça işlevlerini dışa aktarma sıra sayısı ile önerilmemektedir. Çünkü. LIB dosyası sıra ile işlevi arasındaki eşlemeyi içerir, DLL kullanan projelerde normalde yaptığınız gibi işlev adı kullanabilirsiniz.  
  
İsteğe bağlı kullanarak `NONAME` anahtar sözcüğü, yalnızca sıralı olarak dışarı aktarma ve ortaya çıkan DLL'yi dışa aktarma tablosunda boyutunu küçültün. Ancak, kullanmak istiyorsanız [GetProcAddress](http://msdn.microsoft.com/library/windows/desktop/ms683212.aspx) DLL adı geçerli değil çünkü sıra bilmeniz gerekir.  
  
İsteğe bağlı anahtar sözcük `PRIVATE` engeller *GirişAdı* bağlantı tarafından oluşturulan içeri aktarma kitaplığına eklenen öğesinden. Dışa aktarma, ayrıca bağlantı tarafından oluşturulan görüntüyü etkilemez.  
  
İsteğe bağlı anahtar sözcük `DATA` verme kod değil veri olduğunu belirtir. Bu örnek adlı bir veri değişkeni nasıl dışarı aktarılamadı gösterir `exported_global`:  
  
```DEF  
EXPORTS  
   exported_global DATA  
```  
  
Önerilen sırayla yeniden listelenmiş bir tanımını dışarı aktarma için izleyebileceğiniz dört yol vardır:  
  
1.  [__Declspec(dllexport)](../../cpp/dllexport-dllimport.md) kaynak koddaki anahtar sözcüğü  
  
2.  Bir `EXPORTS` deyiminde bir. DEF dosyası  
  
3.  Bir [/dışarı aktarma](../../build/reference/export-exports-a-function.md) bağlantı komut belirtimi  
  
4.  A [yorum](../../preprocessor/comment-c-cpp.md) kaynak kodda, formun yönergesi `#pragma comment(linker, "/export: definition ")`  
  
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

[Modül Tanımlama Deyimleri Kuralları](../../build/reference/rules-for-module-definition-statements.md)
