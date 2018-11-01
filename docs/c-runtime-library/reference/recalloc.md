---
title: _recalloc
ms.date: 11/04/2016
apiname:
- _recalloc
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
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _recalloc
- recalloc
helpviewer_keywords:
- _recalloc function
- recalloc function
ms.assetid: 1db8305a-3f03-418c-8844-bf9149f63046
ms.openlocfilehash: 3bcc238dcb950a8e30af16efc557e99d933efe92
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50436523"
---
# <a name="recalloc"></a>_recalloc

Bir birleşimi **realloc** ve **calloc**. Bir dizi bellek içinde yeniden ayırır ve öğeleri 0 başlatır.

## <a name="syntax"></a>Sözdizimi

```C
void *_recalloc(
   void *memblock
   size_t num,
   size_t size
);
```

### <a name="parameters"></a>Parametreler

*memblock*<br/>
Daha önce ayrılmış bellek bloğuna işaretçi.

*Sayı*<br/>
Öğe sayısı.

*Boyutu*<br/>
Her öğenin bayt cinsinden uzunluğu.

## <a name="return-value"></a>Dönüş Değeri

**_recalloc** döndürür bir **void** yeniden (ve muhtemelen taşınan) bellek bloğuna işaretçi.

Blok için verilen boyuta genişletmek için yeterli kullanılabilir bellek yoksa, özgün blok sol değiştirilmez, ve **NULL** döndürülür.

İstenen boyut sıfırsa sonra blok tarafından işaret edilen *memblock* serbest bırakılır; dönüş değeri **NULL**, ve *memblock* boşaltılmış bloğundaki işaret eden bırakılır.

Dönüş değeri, nesnenin herhangi bir türde bir depolama için uygun şekilde hizalanması garanti bir depolama alanına işaret eder. Dışında bir türe işaretçi almaya **void**, bir tür ataması dönüş değerini kullanın.

## <a name="remarks"></a>Açıklamalar

**_Recalloc** işlev ayrılan bellek blok boyutu değiştirir. *Memblock* bağımsız değişken bellek bloğu başlangıcına işaret eder. Varsa *memblock* olduğu **NULL**, **_recalloc** aynı şekilde davranır [calloc](calloc.md) ve yeni bir bloğu ayırır *numarası*  *  *boyutu* bayt. Her öğe 0 olarak başlatılır. Varsa *memblock* değil **NULL**, önceki bir çağrı tarafından döndürülen bir işaretçi olmalıdır **calloc**, [malloc](malloc.md), veya [realloc ](realloc.md).

Yeni bir blok içinde yeni bir bellek konumuna olabileceğinden, işaretçi tarafından döndürülen **_recalloc** geçtiğini işaretçisi olması garanti edilmez *memblock* bağımsız değişken.

**_recalloc** ayarlar **errno** için **ENOMEM** bellek ayırma başarısız olursa veya bellek miktarını aşıyor istenirse **_HEAP_MAXREQ**. Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz: [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

**recalloc** çağrıları **realloc** C++ kullanmak için [_set_new_mode](set-new-mode.md) yeni işleyici modu ayarlamak için işlevi. Yeni işleyici modunu gösterir mi, hata durumunda, **realloc** tarafından belirlenen yeni işleyici rutinini çağırmaktır [_set_new_handler](set-new-handler.md). Varsayılan olarak, **realloc** bellek dağıtma hatasında yeni işleyici rutinini çağırmaz. Bu varsayılan davranışı geçersiz kılabilirsiniz böylece, **_recalloc** bellek ayırmak başarısız **realloc** aynı yeni işleyici rutinini çağırır biçimi **yeni** işleci aynı nedenden dolayı başarısız olduğunda yapar. Varsayılan geçersiz kılmak için çağırın

```C
_set_new_mode(1);
```

program ya da NEWMODE.OBJ ile erken.

Uygulamayı hata ayıklama sürümü C çalışma zamanı kitaplıkları ile ilişkilendirildiğinde **_recalloc** çözümler [_recalloc_dbg](recalloc-dbg.md). Yığının hata ayıklama işlemi sırasında nasıl yönetildiği hakkında daha fazla bilgi için bkz. [CRT hata ayıklama yığın](/visualstudio/debugger/crt-debug-heap-details).

**_recalloc** işaretlenmiş `__declspec(noalias)` ve `__declspec(restrict)`, işlevin genel değişkenleri garanti edilir ve döndürülen işaretçiye diğer adı değil. Daha fazla bilgi için [noalias](../../cpp/noalias.md) ve [kısıtlama](../../cpp/restrict.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_recalloc**|\<stdlib.h > ve \<malloc.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Bellek Ayırma](../../c-runtime-library/memory-allocation.md)<br/>
[_recalloc_dbg](recalloc-dbg.md)<br/>
[_aligned_recalloc](aligned-recalloc.md)<br/>
[_aligned_offset_recalloc](aligned-offset-recalloc.md)<br/>
[free](free.md)<br/>
[Bağlantı Seçenekleri](../../c-runtime-library/link-options.md)<br/>
