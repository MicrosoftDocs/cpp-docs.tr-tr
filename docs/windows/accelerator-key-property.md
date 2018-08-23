---
title: Hızlandırıcı tuşu özelliği | Microsoft Docs
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
ms.openlocfilehash: 162cb774e985d490385c68bebab01f48222b3616
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42598323"
---
# <a name="accelerator-key-property"></a>Hızlandırıcı Tuşu Özelliği

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

[Hızlandırıcı Özelliklerini Ayarlama](../windows/setting-accelerator-properties.md)  
[Hızlandırıcı Tablosunu Düzenleme](../windows/editing-in-an-accelerator-table.md)  
[Hızlandırıcı Düzenleyicisi](../windows/accelerator-editor.md)