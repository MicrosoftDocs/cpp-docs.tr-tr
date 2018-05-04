---
title: DIŞARI AKTARMA | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 7cc7a9995fdc5be786712752e30015337b9f1607
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="exports"></a>EXPORTS
Dışarı aktarılan adlarını belirtin bir veya daha fazla verme tanımları bir bölümünü veya sıra numaraları işlevleri ya da veri sunar. Her tanım ayrı bir satırda olmalıdır.  
  
```  
EXPORTS  
   definition  
```  
  
## <a name="remarks"></a>Açıklamalar  
 İlk `definition` aynı satır üzerinde olabilir `EXPORTS` anahtar sözcüğü veya bir sonraki satıra. . Bir veya daha fazla DEF dosyası içerebilir `EXPORTS` deyimleri.  
  
 Bir verme sözdizimi `definition` değil:  
  
```  
  
entryname[=internalname] [@ordinal [NONAME]] [[PRIVATE] | [DATA]]  
```  
  
 `entryname` dışarı aktarmak istediğiniz işlevi veya değişkeni addır. Bu gereklidir. Verdiğiniz ad dll adından farklıysa, verme kişinin adı DLL'de kullanarak belirtin `internalname`. Örneğin, bir işlev, DLL dışarı aktarmaları `func1` ve arayanlar olarak kullanmak istediğiniz `func2`, belirtmeniz gerekir:  
  
```  
EXPORTS  
   func2=func1  
```  
  
 Visual C++ derleyicisi için C++ işlevlerini Adlandır kullandığından, düzenlenmiş adı olarak ya da kullanmalıdır `entryname` veya `internalname`, veya dışarı aktarılan işlevleri kullanarak tanımlayın `extern "C"` kaynak kodundaki. Derleyici de kullanmak için C işlevlerini süsler [__stdcall](../../cpp/stdcall.md) bir alt çizgi (_) öneki ve oluşan bir sonek ile çağırma at işareti (@) bağımsız değişken listesinde (ondalık) bayt sayısı ve ardından.  
  
 Derleyici tarafından üretilen düzenlenmiş adlar bulmak için [DUMPBIN](../../build/reference/dumpbin-reference.md) aracını veya bağlayıcı [/MAP](../../build/reference/map-generate-mapfile.md) seçeneği. Düzenlenmiş adlar derleyici özgüdür. Düzenlenmiş adlar veriyorsanız. DEF dosya DLL'e yürütülebilir dosyalar derleyici aynı sürümünü kullanarak da oluşturulmalıdır. Bu çağıran düzenlenmiş adlarında dışarı aktarılan adlarında eşleşmesini sağlar. DEF dosyası.  
  
 Kullanabilirsiniz`ordinal` bir sayı ve işlev adı değil, DLL'nin verme tabloya geçer belirtmek için. Çok sayıda Windows DLL'leri eski kod desteklemek için sıra numaraları verin. DLL boyutunu en aza indirmenize yardımcı olabilir çünkü 16 bit Windows kodda, sıra numaraları kullanmak için ortak. DLL istemciler için eski destek gerekmedikçe işlevleri sıralı olarak dışarı aktarma öneririz yok. Çünkü. LIB dosyası sıra ile işlevi arasındaki eşlemeyi içerir, normalde DLL kullanan projeler yaptığınız gibi işlev adı kullanabilirsiniz.  
  
 İsteğe bağlı kullanarak `NONAME` anahtar sözcüğü yalnızca sıralı olarak dışarı aktarma ve sonuçta elde edilen DLL dışarı aktarım tablosunda boyutunu azaltın. Ancak, kullanmak istiyorsanız, [GetProcAddress](http://msdn.microsoft.com/library/windows/desktop/ms683212.aspx) DLL üzerinde adı geçerli değil çünkü sıra bilmeniz gerekir.  
  
 Optional anahtar sözcüğü `PRIVATE` engeller `entryname` bağlantı tarafından oluşturulan içeri aktarma kitaplığı'nda eklenmesini gelen. Ayrıca bağlantı tarafından oluşturulan görüntü dışa aktarma etkilemez.  
  
 Optional anahtar sözcüğü `DATA` verme kod değil veri olduğunu belirtir. Bu örnek nasıl adlı bir veri değişken dışarı aktarılamadı gösterir `exported_global`:  
  
```  
EXPORTS  
   exported_global DATA  
```  
  
 Önerilen sırasına tanımı, dışarı aktarmak için dört yolu vardır:  
  
1.  [__Declspec(dllexport)](../../cpp/dllexport-dllimport.md) kaynak kodundaki anahtar sözcüğü  
  
2.  Bir `EXPORTS` deyiminde bir. DEF dosyası  
  
3.  Bir [/dışarı aktarma](../../build/reference/export-exports-a-function.md) bağlantı komutunda belirtimi  
  
4.  A [açıklama](../../preprocessor/comment-c-cpp.md) kaynak kodda, formun yönergesi `#pragma comment(linker, "/export: definition ")`  
  
 Tüm dört yöntemleri aynı programda kullanılabilir. BAĞLANTI dışarı aktarmaları içeren bir program oluşturduğunda, ayrıca bir içeri aktarma kitaplığını sürece oluşturduğu bir. EXP dosyası derleme kullanılır.  
  
 Dışarı aktarma bölüm bir örneği burada verilmiştir:  
  
```  
EXPORTS  
   DllCanUnloadNow      @1          PRIVATE  
   DllWindowName = WindowName       DATA  
   DllGetClassObject    @4 NONAME   PRIVATE  
   DllRegisterServer    @7  
   DllUnregisterServer  
```  
  
 Aktardığınızda bir değişken DLL'den kullanarak bir. DEF dosya sahip olmadığınız belirtmek `__declspec(dllexport)` değişkeni üzerinde. Ancak, DLL kullanan herhangi bir dosyada, hala kullanmalısınız `__declspec(dllimport)` veri bildiriminde.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Modül Tanımlama Deyimleri Kuralları](../../build/reference/rules-for-module-definition-statements.md)