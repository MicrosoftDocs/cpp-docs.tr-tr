---
description: 'Daha fazla bilgi edinin: dosya okuma/yazma erişimi sabitleri'
title: Dosya Read-Write erişim sabitleri
ms.date: 11/04/2016
helpviewer_keywords:
- read/write access constants
- write access constants
- access constants for file read/write
- constants [C++], file attributes
- file read/write access constants
ms.assetid: 56cd1d22-39a5-4fcf-bea2-7046d249e8ee
ms.openlocfilehash: 3c1fe6f6125b52f24b35a03c4c517385410f1fae
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224263"
---
# <a name="file-readwrite-access-constants"></a>Dosya Okuma/Yazma Erişimi Sabitleri

## <a name="syntax"></a>Syntax

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
|**a**|Dosyanın sonuna yazmak için açılır (ekleme); Dosya yoksa, önce dosyayı oluşturur. Tüm yazma işlemleri, dosyanın sonunda oluşur. Dosya işaretçisi veya kullanılarak yeniden konumlandırılabilse `fseek` de `rewind` , herhangi bir yazma işlemi yapılmadan önce her zaman dosyanın sonuna geri taşınır. |
|**"r +"**|Hem okuma hem de yazma için açılır. Dosya yoksa veya bulunamazsa, dosyayı açma çağrısı başarısız olur.|
|**"w +"**|Hem okuma hem de yazma için boş bir dosya açar. Verilen dosya varsa, içeriği yok edilir.|
|**"a +"**|**"A"** ile aynıdır, ancak okumayı de sağlar.|

"R +", "w +" ya da "a +" türü belirtildiğinde, hem okuma hem de yazma için izin verilir (dosya "güncelleştirme" için açık olarak kabul edilir). Ancak, okuma ve yazma arasında geçiş yaptığınızda, aradaki `fflush` , `fsetpos` , `fseek` veya `rewind` işlem olmalıdır. Geçerli konum `fsetpos` veya işlem için belirtilebilir `fseek` .

## <a name="see-also"></a>Ayrıca bkz.

[_fdopen, _wfdopen](../c-runtime-library/reference/fdopen-wfdopen.md)<br/>
[fopen, _wfopen](../c-runtime-library/reference/fopen-wfopen.md)<br/>
[freopen, _wfreopen](../c-runtime-library/reference/freopen-wfreopen.md)<br/>
[_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)<br/>
[_popen, _wpopen](../c-runtime-library/reference/popen-wpopen.md)<br/>
[Global sabitler](../c-runtime-library/global-constants.md)
