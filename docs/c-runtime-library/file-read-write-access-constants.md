---
title: Dosya okuma/yazma erişimi sabitleri
ms.date: 11/04/2016
helpviewer_keywords:
- read/write access constants
- write access constants
- access constants for file read/write
- constants [C++], file attributes
- file read/write access constants
ms.assetid: 56cd1d22-39a5-4fcf-bea2-7046d249e8ee
ms.openlocfilehash: 96d146b2e2f0ed82cbdc52b11d92c049da50e2cb
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79438399"
---
# <a name="file-readwrite-access-constants"></a>Dosya Okuma/Yazma Erişimi Sabitleri

## <a name="syntax"></a>Sözdizimi

```
#include <stdio.h>
```

## <a name="remarks"></a>Açıklamalar

Bu sabitler dosya için istenen erişim türünü ("a", "r" veya "w") belirtir. Hem [çeviri modu](../c-runtime-library/file-translation-constants.md) ("b" veya "t") hem de [diske kaydetme modu](../c-runtime-library/commit-to-disk-constants.md) ("c" veya "n") erişim türüyle belirtilebilir.

Erişim türleri bu tabloda açıklanmıştır:

|Erişim türü|Açıklama|
|----------|----------------|
|**sağ**|Okuma için açılır. Dosya yoksa veya bulunamazsa, dosyayı açma çağrısı başarısız olur.|
|**anlatımı**|Yazma için boş bir dosya açar. Verilen dosya varsa, içeriği yok edilir.|
|**a**|Dosyanın sonuna yazmak için açılır (ekleme); Dosya yoksa, önce dosyayı oluşturur. Tüm yazma işlemleri, dosyanın sonunda oluşur. Dosya işaretçisi `fseek` veya `rewind`kullanılarak yeniden konumlandırılabilse de, herhangi bir yazma işlemi yapılmadan önce her zaman dosyanın sonuna geri taşınır. |
|**"r +"**|Hem okuma hem de yazma için açılır. Dosya yoksa veya bulunamazsa, dosyayı açma çağrısı başarısız olur.|
|**"w +"**|Hem okuma hem de yazma için boş bir dosya açar. Verilen dosya varsa, içeriği yok edilir.|
|**"a +"**|**"A"** ile aynıdır, ancak okumayı de sağlar.|

"R +", "w +" ya da "a +" türü belirtildiğinde, hem okuma hem de yazma için izin verilir (dosya "güncelleştirme" için açık olarak kabul edilir). Ancak, okuma ve yazma arasında geçiş yaptığınızda, bir aradaki `fflush`, `fsetpos`, `fseek`veya `rewind` işlemi olmalıdır. `fsetpos` veya `fseek` işlemi için geçerli konum belirtilebilir.

## <a name="see-also"></a>Ayrıca bkz.

[_fdopen, _wfdopen](../c-runtime-library/reference/fdopen-wfdopen.md)<br/>
[fopen, _wfopen](../c-runtime-library/reference/fopen-wfopen.md)<br/>
[freopen, _wfreopen](../c-runtime-library/reference/freopen-wfreopen.md)<br/>
[_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)<br/>
[_popen, _wpopen](../c-runtime-library/reference/popen-wpopen.md)<br/>
[Global Sabitler](../c-runtime-library/global-constants.md)
