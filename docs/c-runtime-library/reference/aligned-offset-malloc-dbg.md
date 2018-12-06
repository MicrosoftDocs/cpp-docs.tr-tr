---
title: _aligned_offset_malloc_dbg
ms.date: 11/04/2016
apiname:
- _aligned_offset_malloc_dbg
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
- _aligned_offset_malloc_dbg
- aligned_offset_malloc_dbg
helpviewer_keywords:
- _aligned_offset_malloc_dbg function
- aligned_offset_malloc_dbg function
ms.assetid: 6c242307-c59e-4d63-aae5-d8cbec8e021c
ms.openlocfilehash: 96fe9e7fda0d0cdfdbfa5462e4f601e3649e2233
ms.sourcegitcommit: beeb77b2976e997debc55b1af35024cc62e62799
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/06/2018
ms.locfileid: "52977725"
---
# <a name="alignedoffsetmallocdbg"></a>_aligned_offset_malloc_dbg

Belirtilen hizalama sınırındaki (yalnızca hata ayıklama sürümü) bellek ayırır.

## <a name="syntax"></a>Sözdizimi

```C
void * _aligned_offset_malloc_dbg(
   size_t size,
   size_t alignment,
   size_t offset,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>Parametreler

*Boyutu*<br/>
İstenen bellek ayırmasının boyutu.

*Hizalama*<br/>
Hizalama değeri 2'in tam sayı üssü olması gerekir.

*uzaklık*<br/>
Hizalama zorlamak için bellek ayırma olan uzaklık.

*Dosya adı*<br/>
Ayırma işlemi istenen kaynak dosyasının adını işaretçisi veya **NULL**.

*LineNumber*<br/>
Satır numarası kaynak dosyada ayırma işlemi burada istendi veya **NULL**.

## <a name="return-value"></a>Dönüş Değeri

Ayrılan bellek bloğuna işaretçi veya **NULL** işlemi başarısız.

## <a name="remarks"></a>Açıklamalar

**_aligned_offset_malloc_dbg** bir hata ayıklama sürümü [_aligned_offset_malloc](aligned-offset-malloc.md) işlevi. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, her çağrı **_aligned_offset_malloc_dbg** çağrısı azaltılır **_aligned_offset_malloc**. Her ikisi de **_aligned_offset_malloc** ve **_aligned_offset_malloc_dbg** taban yığının bellek bloğu ayrılamadı ancak **_aligned_offset_malloc_dbg** birkaç farklı hata ayıklama özellikleri: arabellek bloğu için sızıntılara, test etmek için kullanıcı bölümünü her iki tarafındaki ve *filename*/*linenumber* kökenini belirlemek için bilgi ayırma isteklerini. Bir blok türü parametresiyle belirli ayırma türleri izleme hizalanmış ayırma desteklenen hata ayıklama özelliği değil. Hizalanmış ayırma _NORMAL_BLOCK bloğu türü olarak görünür.

**_aligned_offset_malloc_dbg** ile biraz daha fazla alan istenen bellek bloğu ayırır *boyutu*. Ek alan, hata ayıklama bellek bloklarını bağlantı ve uygulama ile hata ayıklama üstbilgi bilgileri sağlayın ve arabellek üzerine yazmak için hata ayıklama yığını Yöneticisi tarafından kullanılır. Blok atandığında, blok kullanıcı bölümünü 0xCD değeri ile doldurulur ve 0xFD ile doldurulmuş her üzerine yaz arabellek.

**_aligned_offset_malloc_dbg** hizalama iç içe geçmiş bir öğede; gereken olduğu durumlarda kullanışlıdır örneğin hizalama yuvalanan bir sınıf gerekirse.

**_aligned_offset_malloc_dbg** dayanır **malloc**; daha fazla bilgi için bkz: [malloc](malloc.md).

Bu işlev ayarlar **errno** için **ENOMEM** bellek ayırma başarısız olursa veya istenen boyutu büyüktür **_HEAP_MAXREQ**. Hakkında daha fazla bilgi için **errno**, bkz: [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Ayrıca, **_aligned_offset_malloc** kendi parametrelerini doğrular. Varsa *hizalama* 2'in kuvveti değil veya *uzaklığı* büyüktür veya eşittir *boyutu* ve sıfır değilse, bu işlev geçersiz parametre işleyicisi içindeaçıklananşekildeçağırır[ Parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, bu işlevi döndürür **NULL** ve ayarlar **errno** için **EINVAL**.

Nasıl bellek blokları ayrılan, başlatılır ve taban yığının hata ayıklama sürümünde yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).

Ayırma blok türleri ve bunların nasıl kullanıldığı hakkında daha fazla bilgi için bkz. [hata ayıklama öbek üzerindeki blokları türleri](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_aligned_offset_malloc_dbg**|\<crtdbg.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
