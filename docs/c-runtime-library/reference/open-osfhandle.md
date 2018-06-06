---
title: _open_osfhandle | Microsoft Docs
ms.custom: ''
ms.date: 05/29/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _open_osfhandle
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _open_osfhandle
- open_osfhandle
dev_langs:
- C++
helpviewer_keywords:
- open_osfhandle function
- file handles [C++], associating
- _open_osfhandle function
ms.assetid: 30d94df4-7868-4667-a401-9eb67ecb7855
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: af3783420389dc008e39c818c39406f0b2af8af5
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34569842"
---
# <a name="openosfhandle"></a>_open_osfhandle

C çalışma zamanı dosya tanımlayıcısı var olan bir işletim sistemi dosya tanıtıcısı ile ilişkilendirir.

## <a name="syntax"></a>Sözdizimi

```cpp
int _open_osfhandle (
   intptr_t osfhandle,
   int flags
);
```

### <a name="parameters"></a>Parametreler

*osfhandle*<br/>
İşletim sistemi dosya işleci.

*Bayrakları*<br/>
İzin verilen işlem türleri.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, **_open_osfhandle** C çalışma zamanı dosya tanımlayıcısı döndürür. Aksi takdirde, -1 döndürür.

## <a name="remarks"></a>Açıklamalar

**_Open_osfhandle** işlevi C çalışma zamanı dosya tanımlayıcısı ayırır ve tarafından belirtilen işletim sistemi dosya işleci ile ilişkilendirir *osfhandle*. Derleyici Uyarısı önlemek için cast *osfhandle* bağımsız değişkenden **İŞLEMEK** için **intptr_t**. *Bayrakları* değişkeni birinden biçimlendirilmiş bir tamsayı ifade veya daha fazla bildirim sabitleri tanımlanan \<fcntl.h >. İki veya daha fazla bildirim sabitleri forma kullanılan zaman *bayrakları* bağımsız değişkeni, sabitleri bit düzeyinde OR işleci ile birleştirilir ( **&#124;** ).

Bu bildirim sabitleri tanımlanan \<fcntl.h >:

|||
|-|-|
**\_O\_EKLEME**|Dosya işaretçisini her yazma işleminden önce dosyanın sonuna yerleştirir.
**\_O\_RDONLY**|Yalnızca okuma dosyasını açar.
**\_O\_METİN**|Dosya (çevrilmiş) metin modunda açılır.
**\_O\_WTEXT**|Dosya Unicode (çevrilmiş UTF-16) modunda açılır.

**_Open_osfhandle** çağrısı dosya tanımlayıcısı için Win32 dosya işleci sahipliğini aktarır. İle açılmış bir dosyada kapatmak için **_open_osfhandle**, çağrı [ \_kapatmak](close.md). Temel işletim sistemi dosya işleci ayrıca bir çağrı tarafından kapatılan **_close**, Win32 işlevi çağırmak gerekli değildir **CloseHandle** özgün tutamacı. Dosya tanımlayıcısı aitse bir **dosya &#42;**  stream, ardından çağırma [fclose](fclose-fcloseall.md) üzerindeki **dosya &#42;**  akış de her iki dosya tanımlayıcısı kapatır ve temel alınan işleci. Bu durumda, çağırmayın **_close** üzerinde dosya tanımlayıcısı.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_open_osfhandle**|\<io.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dosya İşleme](../../c-runtime-library/file-handling.md)<br/>
