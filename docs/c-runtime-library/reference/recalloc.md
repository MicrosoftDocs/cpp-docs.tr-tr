---
title: _recalloc
ms.date: 4/2/2020
api_name:
- _recalloc
- _o__recalloc
api_location:
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _recalloc
- recalloc
helpviewer_keywords:
- _recalloc function
- recalloc function
ms.assetid: 1db8305a-3f03-418c-8844-bf9149f63046
ms.openlocfilehash: 57972a48336d8dd362b5da7513c854703134921b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338116"
---
# <a name="_recalloc"></a>_recalloc

**Realloc** ve **calloc**bir arada . Bellekteki bir diziyi yeniden tahsis eder ve öğelerini 0'a başlar.

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
Daha önce ayrılmış bellek bloğu için işaretçi.

*number*<br/>
Öğe sayısı.

*Boyutu*<br/>
Her öğenin baytuzunluk.

## <a name="return-value"></a>Dönüş Değeri

**_recalloc,** **geçersiz** bir işaretçiyi yeniden tahsis edilen (ve büyük olasılıkla taşınan) bellek bloğuna döndürür.

Bloğu verilen boyuta genişletmek için yeterli kullanılabilir bellek yoksa, özgün blok değişmeden bırakılır ve **NULL** döndürülür.

İstenen boyut sıfır ise, *memblock* tarafından işaret edilen blok serbest bırakılır; döndürme değeri **NULL'dur**ve *memblock* serbest bırakılmış bir bloğu işaret ederek bırakılır.

İade değeri, herhangi bir nesne türünün depolanması için uygun şekilde hizalanması garanti edilen bir depolama alanına işaret ediyor. **Void**dışında bir tür için bir işaretçi almak için, dönüş değeri bir tür döküm kullanın.

## <a name="remarks"></a>Açıklamalar

_recalloc **_recalloc** işlevi ayrılmış bellek bloğunun boyutunu değiştirir. *Memblock* bağımsız değişkeni bellek bloğunun başlangıcını işaret edersiniz. *memblock* **NULL**ise, **_recalloc** [calloc](calloc.md) aynı şekilde olur ve *sayı* * *boyutu* bayt yeni bir blok ayırır. Her öğe 0'a başharfle verilir. *Memblock* **NULL**değilse, bir işaretçi **calloc,** [malloc,](malloc.md)veya [realloc](realloc.md)önceki bir çağrı tarafından döndürülen olmalıdır.

Yeni blok yeni bir bellek konumunda olabileceğinden, **_recalloc** döndürülen işaretçinin *memblock* bağımsız değişkeninden geçirilen işaretçi olacağı garanti edilmez.

**_recalloc,** bellek ayırma başarısız olursa veya istenen bellek miktarı **_HEAP_MAXREQ**aşarsa **Errno'yu** **ENOM** olarak ayarlar. Bu ve diğer hata kodları hakkında bilgi için [bkz: errno, _doserrno, _sys_errlist ve _sys_nerr.](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)

**recalloc,** yeni işleyici modunu ayarlamak için C++ [_set_new_mode](set-new-mode.md) işlevini kullanmak için **realloc** çağırır. Yeni işleyici modu, hata, **realloc** [_set_new_handler](set-new-handler.md)tarafından ayarlanan yeni işleyici yordamı aramak olup olmadığını gösterir. Varsayılan olarak, **realloc** bellek tahsis başarısız yeni işleyici yordamı aramaz. Bu varsayılan davranışı geçersiz _recalloc bellek **ayırmayı** başaramadığı zaman, **realloc** yeni işleyici yordamını aynı nedenle başarısız olduğunda **yeni** işlecinin yaptığı gibi çağırır. Varsayılanı geçersiz kılmak için,

```C
_set_new_mode(1);
```

programın erken, ya da NEWMODE.OBJ ile bağlantı.

Uygulama C çalışma zamanı kitaplıklarının hata ayıklama sürümüyle bağlantılı olduğunda, **_recalloc** [_recalloc_dbg.](recalloc-dbg.md) Hata ayıklama işlemi sırasında yığının nasıl yönetildiği hakkında daha fazla bilgi için [CRT Hata Ayıklama Yığını'na](/visualstudio/debugger/crt-debug-heap-details)bakın.

**_recalloc** `__declspec(noalias)` işaretlenir `__declspec(restrict)`ve işlevin genel değişkenleri değiştirmemesi ve döndürülen işaretçinin diğer adı olmadığı anlamına gelir. Daha fazla bilgi için [noalias'a](../../cpp/noalias.md) bakın ve [kısıtlayın.](../../cpp/restrict.md)

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_recalloc**|\<stdlib.h> \<ve malloc.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Bellek Ayırma](../../c-runtime-library/memory-allocation.md)<br/>
[_recalloc_dbg](recalloc-dbg.md)<br/>
[_aligned_recalloc](aligned-recalloc.md)<br/>
[_aligned_offset_recalloc](aligned-offset-recalloc.md)<br/>
[Ücret -siz](free.md)<br/>
[Bağlantı Seçenekleri](../../c-runtime-library/link-options.md)<br/>
