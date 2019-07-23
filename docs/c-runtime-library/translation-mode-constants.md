---
title: Çeviri Modu Sabitleri
ms.date: 11/04/2016
f1_keywords:
- _O_BINARY
- _O_TEXT
- _O_RAW
helpviewer_keywords:
- O_BINARY constant
- O_TEXT constant
- O_RAW constant
- _O_TEXT constant
- _O_RAW constant
- translation constants
- _O_BINARY constant
- translation, constants
- translation, modes
- translation modes (file I/O)
ms.assetid: a5993bf4-7e7a-47f9-83c3-e46332b85579
ms.openlocfilehash: a86c0c1a0b70613c6e7749c78f58f6dfb3602d4d
ms.sourcegitcommit: 878a164fe6d550ca81ab87d8425c8d3cd52fe384
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/22/2019
ms.locfileid: "68376284"
---
# <a name="translation-mode-constants"></a>Çeviri Modu Sabitleri

## <a name="syntax"></a>Sözdizimi

```
#include <fcntl.h>
```

## <a name="remarks"></a>Açıklamalar

`_open` `_sopen`Ve bildirim sabitleri, dosyalar (ve) için çeviri modunu veya akışlar (`_setmode`) için çeviri modunu belirleme. `_O_TEXT` `_O_BINARY`

İzin verilen değerler şunlardır:

|||
|-|-|
`_O_TEXT`  | Dosyayı metin (çevrilmiş) modunda açar. Satır başı satır besleme (CR-LF) birleşimleri, girişte tek satırlık bir akışa (LF) çevrilir. Satır akış karakterleri, çıkışta CR-LF birleşimlerine çevrilir. Ayrıca CTRL + Z, girişte bir dosya sonu karakteri olarak yorumlanır. Okuma ve yazma `fopen` için açılan dosyalarda, dosyanın sonunda CTRL + Z olup olmadığını denetler ve mümkünse kaldırır. Bu, CTRL + Z ile `fseek` biten `ftell` bir dosya içinde hareket etmek için ve işlevlerinin kullanılması, dosyanın sonuna doğru `fseek` şekilde davranmasına neden olabileceğinden, yapılır.
`_O_BINARY`  | Dosyayı ikili (çevrilmemiş) modda açar. Yukarıdaki Çeviriler bastırılır.
`_O_RAW`  | `_O_BINARY`Aynı. C 2,0 uyumluluğu için desteklenir.

Daha fazla bilgi için bkz. [metin ve Ikili mod dosyası g/ç](../c-runtime-library/text-and-binary-mode-file-i-o.md) ve [Dosya çevirisi](../c-runtime-library/file-translation-constants.md).

## <a name="see-also"></a>Ayrıca bkz.

[_open, _wopen](../c-runtime-library/reference/open-wopen.md)<br/>
[_pipe](../c-runtime-library/reference/pipe.md)<br/>
[_sopen, _wsopen](../c-runtime-library/reference/sopen-wsopen.md)<br/>
[_setmode](../c-runtime-library/reference/setmode.md)<br/>
[Global Sabitler](../c-runtime-library/global-constants.md)
