---
title: Olay Ekleme Sihirbazı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.event.overview
dev_langs:
- C++
helpviewer_keywords:
- Add Event Wizard [C++]
ms.assetid: bdd2a7bb-13d5-44d7-abc9-e785ba4e05ce
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f83ff02329a373e6ba65315cf33f7cb21145eb48
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46402675"
---
# <a name="add-event-wizard"></a>Olay Ekleme Sihirbazı

Bu sihirbaz, MFC ActiveX denetimi projesi için bir olay ekler. Kendi olay belirtebilirsiniz, genellikle stok olayı özelleştirebilirsiniz veya stok olaylar listesinden seçebilirsiniz.

- **Olay adı**

   Sınıftan olay istemek için Otomasyon istemcileri tarafından kullanılan adını ayarlar. Bir ad girin veya listeden birini seçin.

- **Olay türü**

   Eklenecek olay türünü belirtir. Yalnızca gelen seçerseniz kullanılabilir **olay adı** listesi.

   |Seçenek|Açıklama|
   |------------|-----------------|
   |**Hisse senedi**|Bir düğmeye tıklatma gibi bir stok olayı Bu sınıf için uygulanacak belirtir. Stok olaylar, Microsoft Foundation Class (MFC) Kitaplığı'nda tanımlanır.|
   |**Özel**|Olayın kendi uygulamanız sağlama belirtir.|

- **İç adı**

   Olayı gönderen üye işlevinin adını ayarlar. Yalnızca özel olaylar için kullanılabilir. Ad temel **olay adı**. Farklı bir ad verin istiyorsanız iç adını değiştirebilirsiniz **olay adı**.

- **Parametre türü**

   Tür için ayarlar **parametre adı**. Türü listeden seçin.

- **Parametre adı**

   Etkinliğiniz geçmek için bir parametre adını ayarlar. Adını yazdıktan sonra tıklamanız **Ekle** parametre listesi eklemek için.

   ' A tıkladığınızda **Ekle**, parametre adı görünür **parametre listesi**.

   > [!NOTE]
   > Parametre adı sağlayın ve ardından **son** tıklamadan önce **Ekle**, sonra parametre olaya eklenmez. Yöntemini bulun ve parametre el ile Ekle gerekir. **Parametre listesi**

- **Add**

   Belirttiğiniz parametre ekler **parametre adı**ve onun türü için **parametre listesi**. ' A tıklamalıdır **Ekle** parametre listesine eklenecek.

- **Kaldır**

   Seçtiğiniz parametre kaldırır **parametre listesi** listeden.

- **Parametre listesi**

   Tüm parametreler ve şu anda yöntemi için eklenen türleri görüntüler. Parametre ekleme gibi sihirbaz güncelleştirir **parametre listesi** her parametre türü ile görüntülenecek.

## <a name="see-also"></a>Ayrıca Bkz.

[Olay ekleme](../ide/adding-an-event-visual-cpp.md)