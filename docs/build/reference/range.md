---
title: /RANGE
ms.date: 11/04/2016
f1_keywords:
- /RANGE
helpviewer_keywords:
- /RANGE dumpbin option
- -RANGE dumpbin option
ms.assetid: 7eeba266-32be-49cc-a350-96bdf541f98a
ms.openlocfilehash: c631057e47e1a52a58d2b1304133dfdfc008ae14
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62319713"
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

## <a name="see-also"></a>Ayrıca bkz.

[DUMPBIN Seçenekleri](dumpbin-options.md)
