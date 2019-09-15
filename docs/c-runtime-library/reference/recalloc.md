---
title: _recalloc
ms.date: 11/04/2016
api_name:
- _recalloc
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
ms.openlocfilehash: f06631fe4dd0abcb0b18895ccb04e5b52cda6a2c
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70949440"
---
# <a name="_recalloc"></a>_recalloc

**Realloc** ve **calloc**birleşimi. Bellekte bir diziyi yeniden konumlandırır ve öğelerini 0 olarak başlatır.

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
Önceden ayrılmış bellek bloğuna yönelik işaretçi.

*sayısından*<br/>
Öğe sayısı.

*boyutla*<br/>
Her öğenin bayt cinsinden uzunluğu.

## <a name="return-value"></a>Dönüş Değeri

**_yeniden hesapla** geri ayrılan (ve muhtemelen taşınan) bellek bloğuna **void** bir işaretçi döndürür.

Bloğu verilen boyuta genişletmek için yeterli kullanılabilir bellek yoksa, özgün blok değiştirilmeden bırakılır ve **null** döndürülür.

İstenen boyut sıfırsa, *memblock* tarafından işaret edilen blok serbest bırakılır; dönüş değeri **null**ve *memblock* serbest bırakılmış bir blok üzerine gelindiğinde bırakılır.

Dönüş değeri, herhangi bir nesne türünün depolanması için uygun şekilde hizalı olarak garantili bir depolama alanına işaret eder. **Void**dışında bir türe işaretçi almak için, dönüş değerinde bir tür dönüştürme kullanın.

## <a name="remarks"></a>Açıklamalar

**_Yeniden hesapla** işlevi, ayrılmış bir bellek bloğunun boyutunu değiştirir. *Memblock* bağımsız değişkeni bellek bloğunun başlangıcına işaret eder. *Memblock* **null**ise, **_yeniden hesapla** [calloc](calloc.md) ile aynı şekilde davranır ve bir *sayı* * *boyutu* baytları için yeni bir blok ayırır. Her öğe 0 olarak başlatılır. *Memblock* **null**değilse, bir önceki **calloc**, [malloc](malloc.md)veya [realloc](realloc.md)çağrısıyla döndürülen bir işaretçi olmalıdır.

Yeni blok yeni bir bellek konumunda olabileceğinden, **_yeniden hesapla** tarafından döndürülen işaretçinin *memblock* bağımsız değişkeniyle geçen işaretçi olması garanti edilmez.

**_yeniden hesapla** , bellek ayırma başarısız olursa veya istenen bellek miktarı **_Heap_maxreq**değerini aşarsa, **errno** değeri **ENOMEM** olarak ayarlanır. Bu ve diğer hata kodları hakkında bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

yeni işleyici modunu ayarlamak için [_set_new_mode](set-new-mode.md) işlevini kullanmak üzere yeniden C++ **Hesaplama** işlemi, **realloc** ' i çağırır. Yeni işleyici modu, hata durumunda, **realloc** 'ın, [_set_new_handler](set-new-handler.md)tarafından ayarlanan yeni işleyici yordamını çağırıp çağırmayacağını gösterir. Varsayılan olarak, **realloc** bellek ayırma hatası üzerine yeni işleyici yordamını çağırmaz. Bu varsayılan davranışı geçersiz kılabilirsiniz; böylelikle, **_yeniden hesapla** bellek ayıramadığında, **realloc** yeni işleyici yordamını aynı nedenle başarısız olduğunda **Yeni** işlecin yaptığı şekilde çağırır. Varsayılanı geçersiz kılmak için şunu çağırın

```C
_set_new_mode(1);
```

Programın başlarında veya NEWMODE. OBJ ile bağlantılandırın.

Uygulama, C çalışma zamanı kitaplıklarının hata ayıklama sürümüyle bağlantılı olduğunda, **_yeniden hesapla** lt [_dbg](recalloc-dbg.md)olarak çözümleniyor. Hata ayıklama işlemi sırasında yığının nasıl yönetildiği hakkında daha fazla bilgi için bkz. [CRT hata ayıklama yığını](/visualstudio/debugger/crt-debug-heap-details).

**_yeniden hesapla** `__declspec(noalias)` , ve `__declspec(restrict)`işlevin genel değişkenleri değiştirmeyeceği garantisi ve döndürülen işaretçinin diğer adı olmadığı anlamına gelir. Daha fazla bilgi için bkz. [noalias](../../cpp/noalias.md) ve [Restrict](../../cpp/restrict.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_recalloc**|\<Stdlib. h > ve \<malloc. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Bellek Ayırma](../../c-runtime-library/memory-allocation.md)<br/>
[_recalloc_dbg](recalloc-dbg.md)<br/>
[_aligned_recalloc](aligned-recalloc.md)<br/>
[_aligned_offset_recalloc](aligned-offset-recalloc.md)<br/>
[free](free.md)<br/>
[Bağlantı Seçenekleri](../../c-runtime-library/link-options.md)<br/>
