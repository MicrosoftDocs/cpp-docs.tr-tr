---
description: 'Daha fazla bilgi edinin: dosya çevirisi sabitleri'
title: Dosya Çeviri Sabitleri
ms.date: 11/04/2016
helpviewer_keywords:
- translation constants
- file translation [C++], constants
- translation, file translation constants
- translation, constants
- constants [C++], file translation mode
- file translation [C++]
ms.assetid: 49b13bf3-442e-4d19-878b-bd1029fa666a
ms.openlocfilehash: 75bb54c7e038efd41ed22ec941d871f6fbc54b7c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332983"
---
# <a name="file-translation-constants"></a>Dosya Çeviri Sabitleri

## <a name="syntax"></a>Syntax

```
#include <stdio.h>
```

## <a name="remarks"></a>Açıklamalar

Bu sabitler, çeviri modunu belirtir (**"b"** veya **"t"**). Modu, erişim türünü belirten dizeye dahildir (**"r"**, " **w"**, **"a"**, **"r +"**, **"w +"**, **"a +"**).

Çeviri modları aşağıdaki gibidir:

- **şı**

   Metin (çevrilmiş) modunda açılır. Bu modda, satır başı satır besleme (CR-LF) birleşimleri girişte tek satırlık akışlara (LF) çevrilir ve LF karakterleri çıkışta CR-LF birleşimlerine çevrilir. Ayrıca CTRL + Z, girişte bir dosya sonu karakteri olarak yorumlanır. Okuma veya okuma ve yazma için açılan dosyalarda, `fopen` dosyanın sonunda CTRL + Z olup olmadığını denetler ve mümkünse kaldırır. Bu, `fseek` `ftell` CTRL + Z ile biten bir dosya içinde hareket etmek için ve işlevlerinin kullanılması, `fseek` dosyanın sonuna doğru şekilde davranmasına neden olabileceğinden, yapılır.

   > [!NOTE]
   > **T** seçeneği ve için ANSI standardının bir parçası değildir `fopen` `freopen` . Bu bir Microsoft uzantısıdır ve ANSI taşınabilirliği istendiği yerde kullanılmamalıdır.

- **kenarı**

   İkili (çevrilmemiş) modda açılır. Yukarıdaki Çeviriler bastırılır.

**T** veya **b** *modda* verilmezse, çeviri modu [_fmode](../c-runtime-library/fmode.md)varsayılan mod değişkeni tarafından tanımlanır. Metin ve ikili modları kullanma hakkında daha fazla bilgi için bkz. [metin ve Ikili mod dosya g/ç](../c-runtime-library/text-and-binary-mode-file-i-o.md).

## <a name="see-also"></a>Ayrıca bkz.

[_fdopen, _wfdopen](../c-runtime-library/reference/fdopen-wfdopen.md)<br/>
[fopen, _wfopen](../c-runtime-library/reference/fopen-wfopen.md)<br/>
[freopen, _wfreopen](../c-runtime-library/reference/freopen-wfreopen.md)<br/>
[_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)<br/>
[Global sabitler](../c-runtime-library/global-constants.md)
