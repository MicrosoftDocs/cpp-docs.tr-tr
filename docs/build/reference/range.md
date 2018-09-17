---
title: -RANGE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /RANGE
dev_langs:
- C++
helpviewer_keywords:
- /RANGE dumpbin option
- -RANGE dumpbin option
ms.assetid: 7eeba266-32be-49cc-a350-96bdf541f98a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 47e7525b8c1872616182141d624bff8f94571952
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45712198"
---
# <a name="range"></a>/RANGE

/RAWDATA veya /DISASM gibi diğer DUMPBIN seçenekleri ile birlikte kullanıldığında dumpbin çıktısını değiştirir.

## <a name="syntax"></a>Sözdizimi

```
/RANGE:vaMin[,vaMax]
```

## <a name="parameters"></a>Parametreler

*vaMin*<br/>
Başlamak için DUMPBIN işlemi istediğiniz sanal adres.

*vaMax*<br/>
(İsteğe bağlı) DUMPBIN işlemi sonlandırmak için istediğiniz sanal adres. Belirtilmezse, dosyanın sonuna dumpbin geçer.

## <a name="remarks"></a>Açıklamalar

Görüntü sanal adreslerini görmek için eşleme dosyası (RVA + Base) görüntüsü için kullandığınız **/DISASM** veya **OPTIONAL** dumpbin veya Visual Studio hata ayıklayıcısını ayrıştırma penceresinde seçeneği.

## <a name="example"></a>Örnek

Bu örnekte, **/aralığı** görüntülenme durumunu değiştirmek için kullanılan **/disasm** seçeneği. Bu örnekte, başlangıç değeri bir ondalık sayı olarak ifade edilir ve bitiş değeri, onaltılık bir sayı belirtilir.

```
dumpbin /disasm /range:4219334,0x004061CD t.exe
```

## <a name="see-also"></a>Ayrıca Bkz.

[DUMPBIN Seçenekleri](../../build/reference/dumpbin-options.md)