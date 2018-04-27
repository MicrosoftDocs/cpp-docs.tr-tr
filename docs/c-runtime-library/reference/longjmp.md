---
title: longjmp | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- longjmp
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- longjmp
dev_langs:
- C++
helpviewer_keywords:
- restoring stack environment and execution locale
- longjmp function
ms.assetid: 0e13670a-5130-45c1-ad69-6862505b7a2f
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0a593c2dcdfe1731ee5c6438c7a330e7f4ea8740
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="longjmp"></a>longjmp

Geri Yükleme ortamını ve yürütme yerel yığın.

## <a name="syntax"></a>Sözdizimi

```C
void longjmp(
   jmp_buf env,
   int value
);
```

### <a name="parameters"></a>Parametreler

*env* hangi ortam depolanan değişkeni.

*değer* için döndürülecek değer **setjmp** çağırın.

## <a name="remarks"></a>Açıklamalar

**Longjmp** işlevi geri yükler, daha önce kaydedilmiş bir yığın ortamını ve yürütme yerel *env* tarafından **setjmp**. **setjmp** ve **longjmp** bir yerel olmayan yürütmek için bir yol sağlamak **goto**; bunlar genellikle daha önce çağrılan bir yordam hata işleme veya kurtarma kodunda yürütme denetimi geçirmek için kullanılır normal çağır ve dönüş kurallarını kullanma.

Çağrı **setjmp** kaydedilmesi geçerli yığın ortamını neden *env*. Sonraki çağrı **longjmp** kaydedilmiş ortamı geri yükler ve karşılık gelen hemen ardından noktasına denetimini döndürür **setjmp** çağırın. Yürütme sürdürür gibi *değeri* tarafından yalnızca iade edildi **setjmp** çağırın. Denetim alma yordamı erişilebilir (yazmaç değişkenleri dışında) tüm değişkenlerin değerleri, sahip oldukları zaman değerleri içeren **longjmp** çağrıldı. YAZMAÇ değişkenlerin değerleri tahmin edilemez. Tarafından döndürülen değer **setjmp** sıfır olmalıdır. Varsa *değeri* geçirilen gerçek dönüş 1 değerini 0 değiştirilir.

Çağrı **longjmp** işleve önce **setjmp** döndürür; Aksi takdirde sonuçlar tahmin edilemez.

Kullanırken aşağıdaki kısıtlamalar gözlemlemek **longjmp**:

- YAZMAÇ değişkenlerin değerleri aynı kalacaksa varsayalım değil. Rutin arama kaydı değişkenlerin değerleri **setjmp** sonra uygun değerlere geri **longjmp** yürütülür.

- Kullanmayın **longjmp** kesme bir kayan nokta özel durumu nedeniyle sürece denetimi dışında bir kesme işleme yordamı aktarmak için. Bu durumda, bir program bir kesme işleyicisinden döndürebilir **longjmp** , ilk kayan nokta Matematiği paket çağırarak yeniden başlatır, **_fpreset**.

     **Not** kullanırken dikkatli olun **setjmp** ve **longjmp** C++ programlarında. Bu işlevler C++ nesne semantiği desteklemediği için C++ özel durum işleme mekanizmasının kullanılması daha güvenlidir.

Daha fazla bilgi için bkz: [setjmp ve longjmp kullanma](../../cpp/using-setjmp-longjmp.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**longjmp**|\<setjmp.h'ı >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Örnek

Örneğin bkz [_fpreset](fpreset.md).

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[setjmp](setjmp.md)<br/>
