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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 45f483bcaa397969a81097768ebbd1ed4cda288b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226196"
---
# <a name="_recalloc"></a>_recalloc

**Realloc** ve **calloc**birleşimi. Bellekte bir diziyi yeniden konumlandırır ve öğelerini 0 olarak başlatır.

## <a name="syntax"></a>Söz dizimi

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

*sayı*<br/>
Öğe sayısı.

*boyutla*<br/>
Her öğenin bayt cinsinden uzunluğu.

## <a name="return-value"></a>Dönüş Değeri

**_recalloc** **`void`** , yeniden ayrılan (ve muhtemelen taşınan) bellek bloğuna bir işaretçi döndürür.

Bloğu verilen boyuta genişletmek için yeterli kullanılabilir bellek yoksa, özgün blok değiştirilmeden bırakılır ve **null** döndürülür.

İstenen boyut sıfırsa, *memblock* tarafından işaret edilen blok serbest bırakılır; dönüş değeri **null**ve *memblock* serbest bırakılmış bir blok üzerine gelindiğinde bırakılır.

Dönüş değeri, herhangi bir nesne türünün depolanması için uygun şekilde hizalı olarak garantili bir depolama alanına işaret eder. Dışında bir türe işaretçi almak için **`void`** , dönüş değerinde bir tür dönüştürme kullanın.

## <a name="remarks"></a>Açıklamalar

**_Recalloc** işlevi, ayrılmış bir bellek bloğunun boyutunu değiştirir. *Memblock* bağımsız değişkeni bellek bloğunun başlangıcına işaret eder. *Memblock* **null**ise, **_recalloc** [calloc](calloc.md) ile aynı şekilde davranır ve bir *sayı*  *  *boyutu* baytları için yeni bir blok ayırır. Her öğe 0 olarak başlatılır. *Memblock* **null**değilse, bir önceki **calloc**, [malloc](malloc.md)veya [realloc](realloc.md)çağrısıyla döndürülen bir işaretçi olmalıdır.

Yeni blok yeni bir bellek konumunda olabileceğinden, **_recalloc** tarafından döndürülen işaretçinin *memblock* bağımsız değişkeniyle geçen işaretçi olması garanti edilmez.

bellek ayırma başarısız olursa veya istenen bellek miktarı **_HEAP_MAXREQ**aşarsa, **_recalloc** **errno** değerini **ENOMEM** olarak ayarlar. Bu ve diğer hata kodları hakkında bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

yeni işleyici modunu ayarlamak için C++ [_set_new_mode](set-new-mode.md) işlevini kullanmak üzere yeniden **Hesaplama** işlemi, **realloc** ' i çağırır. Yeni işleyici modu, hata durumunda, **realloc** 'ın [_set_new_handler](set-new-handler.md)tarafından ayarlanan yeni işleyici yordamını çağırıp çağırmayacağını gösterir. Varsayılan olarak, **realloc** bellek ayırma hatası üzerine yeni işleyici yordamını çağırmaz. Bu varsayılan davranışı geçersiz kılabilirsiniz, bu sayede **_recalloc** bellek ayıramadığında, **realloc** yeni işleyici yordamını **`new`** aynı nedenle başarısız olduğunda işlecin yaptığı şekilde çağırır. Varsayılanı geçersiz kılmak için şunu çağırın

```C
_set_new_mode(1);
```

Programın başlarında veya NEWMODE. OBJ ile bağlantılandırın.

Uygulama, C çalışma zamanı kitaplıklarının bir hata ayıklama sürümü ile bağlantılı olduğunda **_recalloc** [_recalloc_dbg](recalloc-dbg.md)çözümlenir. Hata ayıklama işlemi sırasında yığının nasıl yönetildiği hakkında daha fazla bilgi için bkz. [CRT hata ayıklama yığını](/visualstudio/debugger/crt-debug-heap-details).

**_recalloc** `__declspec(noalias)` `__declspec(restrict)` , ve işlevin genel değişkenleri değiştirmeyeceği garantisini olduğu ve döndürülen işaretçinin diğer adı olmadığı anlamına gelir. Daha fazla bilgi için bkz. [noalias](../../cpp/noalias.md) ve [Restrict](../../cpp/restrict.md).

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_recalloc**|\<stdlib.h> ve \<malloc.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Bellek ayırma](../../c-runtime-library/memory-allocation.md)<br/>
[_recalloc_dbg](recalloc-dbg.md)<br/>
[_aligned_recalloc](aligned-recalloc.md)<br/>
[_aligned_offset_recalloc](aligned-offset-recalloc.md)<br/>
[Süz](free.md)<br/>
[Bağlantı seçenekleri](../../c-runtime-library/link-options.md)<br/>
