---
title: Bir olay ekleyin
ms.date: 11/12/2018
f1_keywords:
- vc.codewiz.event.overview
helpviewer_keywords:
- ActiveX controls [C++], adding events to
- MFC ActiveX controls [C++], adding events
- events [C++], ActiveX controls
- add event wizard [C++]
ms.assetid: fe34832a-edfc-4f86-aacb-8df77001873d
ms.openlocfilehash: 1d5a8f5666dd04e00f8a438fdbf00320c37e14f4
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64346017"
---
# <a name="add-an-event"></a>Bir olay ekleyin

Sınıf Görünümü'ndeki kullanarak bir olay ekleyebilirsiniz [olay Ekleme Sihirbazı](#add-event-wizard) denetimi sınıfta için yalnızca, [MFC ActiveX denetimi](../mfc/reference/creating-an-mfc-activex-control.md) proje. Başka türde bir proje için bir olay eklemek istediğiniz kullanırsanız **olayları** düğmesine [Özellikler penceresi](/visualstudio/ide/reference/properties-window).

**MFC ActiveX denetimi projenize bir olay eklemek için:**

1. Sınıf Görünümü'nde projeye sınıflarını görüntülemek için proje düğümünü genişletin.

1. Projenin denetim sınıfı sağ tıklayın.

1. Kısayol menüsünde **Ekle**ve ardından **olay Ekle** olay Ekleme Sihirbazı'nı görüntülemek için.

1. Uygun Sihirbazı kutulara olay bilgilerini sağlayın.

1. Seçin **son** olay projeye eklenecek.

## <a name="in-this-section"></a>Bu bölümde

- [Olay Ekleme Sihirbazı](#add-event-wizard)

## <a name="add-event-wizard"></a>Olay Ekleme Sihirbazı

Bu sihirbaz, MFC ActiveX denetimi projesi için bir olay ekler. Kendi olay belirtin, tipik bir stok olayı özelleştirin veya stok olaylar listesinden seçin.

- **Olay adı**

   Sınıftan olay istemek için Otomasyon istemcileri tarafından kullanılan adını ayarlar. Bir ad girin veya listeden birini seçin.

- **Olay türü**

   Eklenecek olay türünü belirtir. Yalnızca gelen seçerseniz kullanılabilir **olay adı** listesi.

   |Seçenek|Açıklama|
   |------------|-----------------|
   |**Hisse senedi**|Bir düğmeye tıklatma gibi bir stok olayı Bu sınıf için uygulanacak belirtir. Stok olaylar, Microsoft Foundation Class (MFC) Kitaplığı'nda tanımlanır.|
   |**Özel**|Olayın kendi uygulamanız kullandığınız belirtir.|

- **İç adı**

   Olayı gönderen üye işlevinin adını ayarlar. Yalnızca özel olaylar için kullanılabilir. Ad temel **olay adı**. Farklı bir ad verin istiyorsanız iç adını değiştirebilirsiniz **olay adı**.

- **Parametre türü**

   Tür için ayarlar **parametre adı**. Türü listeden seçin.

- **Parametre adı**

   Etkinliğiniz geçmek için bir parametre adını ayarlar. Adını yazdıktan sonra seçmelisiniz **Ekle** parametre listesi eklemek için.

   Seçtiğinizde **Ekle**, parametre adı görünür **parametre listesi**.

   > [!NOTE]
   > Parametre adı sağlayın ve ardından **son** seçtiğiniz önce **Ekle**, sonra parametre olaya eklenmez. Yöntemini bulun ve parametre el ile Ekle gerekir.

- **Add**

   Belirttiğiniz parametre ekler **parametre adı**ve onun türü için **parametre listesi**. Seçin **Ekle** parametre listesine eklenecek.

- **Kaldır**

   Seçtiğiniz parametre kaldırır **parametre listesi** listeden.

- **Parametre listesi**

   Tüm parametreler ve şu anda yöntemi için eklenen türleri görüntüler. Parametre ekleme gibi sihirbaz güncelleştirir **parametre listesi** her parametre türü ile görüntülenecek.
