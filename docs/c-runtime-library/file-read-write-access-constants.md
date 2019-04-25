---
title: Dosya okuma / yazma erişimi sabitleri
ms.date: 11/04/2016
f1_keywords:
- c.constants.file
helpviewer_keywords:
- read/write access constants
- write access constants
- access constants for file read/write
- constants [C++], file attributes
- file read/write access constants
ms.assetid: 56cd1d22-39a5-4fcf-bea2-7046d249e8ee
ms.openlocfilehash: 0dfbc925c5252724cbb1caad58470849915242a9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62289903"
---
# <a name="file-readwrite-access-constants"></a>Dosya Okuma/Yazma Erişimi Sabitleri

## <a name="syntax"></a>Sözdizimi

```
#include <stdio.h>
```

## <a name="remarks"></a>Açıklamalar

Bu sabitler, dosya için istenen erişim türünü ("a", "r" veya "w") belirtin. Her iki [çeviri modu](../c-runtime-library/file-translation-constants.md) ("b" veya "t") ve [işleme disk modu](../c-runtime-library/commit-to-disk-constants.md) ("c" veya "n") erişim türü ile belirtilebilir.

Erişim türleri bu tabloda açıklanmıştır:

|Erişim türü|Açıklama|
|----------|----------------|
|**"r"**|Okuma için açar. Dosya yok veya nebyla nalezena dosyayı açmak için bir çağrı başarısız olur.|
|**"w"**|Yazma için boş bir dosya açar. Verilen dosya varsa içeriği yok edilir.|
|**"a"**|(Ekleme); dosyanın sonunda yazma için açar henüz yoksa, dosyayı ilk oluşturur. Tüm işlemleri dosyanın sonunda gerçekleşmesi yazın. Dosya işaretçisi kullanılarak konumlandırılabilir rağmen `fseek` veya `rewind`, herhangi bir işlemi yazma önce her zaman geri dosyanın sonuna kadar taşınır. |
|**"r +"**|Hem okuma ve yazma için açar. Dosya yok veya nebyla nalezena dosyayı açmak için bir çağrı başarısız olur.|
|**"w +"**|Hem okuma ve yazma için boş bir dosya açar. Verilen dosya varsa içeriği yok edilir.|
|**"a+"**|Aynı **"a"** ancak okuma de sağlar.|

"R +", "w +" veya "a +" türü belirtildiğinde, hem okumaya hem yazmaya izin verilir (dosyanın "güncelleştirme" açık olarak kabul edilir). Ancak, yazma ve okuma arasında geçiş yaptığınızda, olmalıdır bir araya giren `fflush`, `fsetpos`, `fseek`, veya `rewind` işlemi. Geçerli konum için belirtilen `fsetpos` veya `fseek` işlemi.

## <a name="see-also"></a>Ayrıca bkz.

[_fdopen, _wfdopen](../c-runtime-library/reference/fdopen-wfdopen.md)<br/>
[fopen, _wfopen](../c-runtime-library/reference/fopen-wfopen.md)<br/>
[freopen, _wfreopen](../c-runtime-library/reference/freopen-wfreopen.md)<br/>
[_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)<br/>
[_popen, _wpopen](../c-runtime-library/reference/popen-wpopen.md)<br/>
[Global Sabitler](../c-runtime-library/global-constants.md)
