---
title: Hızlandırıcı tuşu özelliği (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Key property
ms.assetid: d1570cd9-b414-4cd6-96bd-47c38281eaca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e0594e5b9e2d092330664546cbd05ccfb0060c42
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46428973"
---
# <a name="accelerator-key-property-c"></a>Hızlandırıcı tuşu özelliği (C++)

Hızlandırıcı tablosu bir anahtar özellik için yasal girişleri şunlardır:

- 0 ve 255 ondalık biçiminde arasında bir tamsayı. Değer, değer ASCII veya ANSI şu şekilde işlenir olup olmadığını belirler:

   - Tek basamaklı sayı her zaman ASCII veya ANSI değerleri olarak değil, karşılık gelen anahtar olarak yorumlanır.

   - 1 ila 26, önünde sıfır ile zaman değerlerini olarak yorumlanır ^ A-^ alfabedeki ile basıldığında ASCII değeri temsil eden Z **Ctrl** tuşu basılı tutularak.

   - 27-32 değerlerinden her zaman üç basamaklı ondalık değerler 032 aracılığıyla 027 olarak yorumlanır.

   - 033 ile 255'den 0'ın öncesinde ya da ANSI değerleri olarak yorumlanmadı değerleri.

- Tek klavye karakter. A - Z büyük harf veya sayı 0 - 9 ASCII veya sanal anahtar değerleri olabilir; başka bir karakter yalnızca ASCII'dir.

- Bir tek klavye karakter aralığı A - Z (yalnızca büyük), öncesinde bir şapka (^) (örneğin, ^ C). Bu anahtarın ASCII değeri, ile basıldığında girer **Ctrl** tuşu basılı tutularak.

   > [!NOTE]
   > ASCII değeri girerken değiştiricisi özellik seçenekleri sınırlıdır. Yalnızca denetim kullanılabilir için anahtar kullanımı **Alt** anahtarı.

- Herhangi bir geçerli sanal anahtar tanımlayıcı. Hızlandırıcı tablosu açılan anahtar kutusunda standart sanal anahtarı tanımlayıcıları listesini içerir.

   > [!TIP]
   > Hızlandırıcı tuşunu tanımlamak için başka bir yolu ise Hızlandırıcı tablosunda birden çok girişlere sağ tıklayın, seçin **sonraki anahtarı yazılan** kısayol menüsünden anahtarlar veya tuş birleşimleri birini klavyede tuşuna basın. **Sonraki anahtarı yazılan** komutu kullanılabilir ayrıca **Düzenle** menüsü.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Hızlandırıcı Özelliklerini Ayarlama](../windows/setting-accelerator-properties.md)<br/>
[Hızlandırıcı Tablosunu Düzenleme](../windows/editing-in-an-accelerator-table.md)<br/>
[Hızlandırıcı Düzenleyicisi](../windows/accelerator-editor.md)