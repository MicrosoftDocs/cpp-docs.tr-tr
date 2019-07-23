---
title: Dosya Çeviri Sabitleri
ms.date: 11/04/2016
f1_keywords:
- c.constants.file
helpviewer_keywords:
- translation constants
- file translation [C++], constants
- translation, file translation constants
- translation, constants
- constants [C++], file translation mode
- file translation [C++]
ms.assetid: 49b13bf3-442e-4d19-878b-bd1029fa666a
ms.openlocfilehash: ed2fae935850837ebace880d78c206754b3061bd
ms.sourcegitcommit: 878a164fe6d550ca81ab87d8425c8d3cd52fe384
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/22/2019
ms.locfileid: "68375922"
---
# <a name="file-translation-constants"></a>Dosya Çeviri Sabitleri

## <a name="syntax"></a>Sözdizimi

```
#include <stdio.h>
```

## <a name="remarks"></a>Açıklamalar

Bu sabitler, çeviri modunu belirtir ( **"b"** veya **"t"** ). Modu, erişim türünü belirten dizeye dahildir ( **"r"** , " **w"** , **"a"** , **"r +"** , **"w +"** , **"a +"** ).

Çeviri modları aşağıdaki gibidir:

- **şı**

   Metin (çevrilmiş) modunda açılır. Bu modda, satır başı satır besleme (CR-LF) birleşimleri girişte tek satırlık akışlara (LF) çevrilir ve LF karakterleri çıkışta CR-LF birleşimlerine çevrilir. Ayrıca CTRL + Z, girişte bir dosya sonu karakteri olarak yorumlanır. Okuma veya okuma ve yazma için açılan dosyalarda, `fopen` dosyanın sonunda CTRL + Z olup olmadığını denetler ve mümkünse kaldırır. Bu, CTRL + Z ile `fseek` biten `ftell` bir dosya içinde hareket etmek için ve işlevlerinin kullanılması, dosyanın sonuna doğru `fseek` şekilde davranmasına neden olabileceğinden, yapılır.

   > [!NOTE]
   > **T** seçeneği ve `fopen` `freopen`için ANSI standardının bir parçası değildir. Bu bir Microsoft uzantısıdır ve ANSI taşınabilirliği istendiği yerde kullanılmamalıdır.

- **b**

   İkili (çevrilmemiş) modda açılır. Yukarıdaki Çeviriler bastırılır.

**T** veya **b** *modunda*verilmezse, çeviri modu varsayılan mod değişkeni [_fmode](../c-runtime-library/fmode.md)tarafından tanımlanır. Metin ve ikili modları kullanma hakkında daha fazla bilgi için bkz. [metin ve Ikili mod dosya g/ç](../c-runtime-library/text-and-binary-mode-file-i-o.md).

## <a name="see-also"></a>Ayrıca bkz.

[_fdopen, _wfdopen](../c-runtime-library/reference/fdopen-wfdopen.md)<br/>
[fopen, _wfopen](../c-runtime-library/reference/fopen-wfopen.md)<br/>
[freopen, _wfreopen](../c-runtime-library/reference/freopen-wfreopen.md)<br/>
[_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)<br/>
[Global Sabitler](../c-runtime-library/global-constants.md)
