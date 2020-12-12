---
description: 'Daha fazla bilgi edinin: olay ekleme'
title: Olay ekleme
ms.date: 11/12/2018
f1_keywords:
- vc.codewiz.event.overview
helpviewer_keywords:
- ActiveX controls [C++], adding events to
- MFC ActiveX controls [C++], adding events
- events [C++], ActiveX controls
- add event wizard [C++]
ms.assetid: fe34832a-edfc-4f86-aacb-8df77001873d
ms.openlocfilehash: c369be0fe241867b101ab458344ae706b1fd440d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97240825"
---
# <a name="add-an-event"></a>Olay ekleme

Sınıf Görünümü, yalnızca [MFC ActiveX denetim](../mfc/reference/creating-an-mfc-activex-control.md) projenizdeki denetim sınıfına [olay Ekleme Sihirbazı](#add-event-wizard) 'nı kullanarak bir olay ekleyebilirsiniz. Başka bir proje türüne olay eklemek istiyorsanız, [Özellikler penceresi](/visualstudio/ide/reference/properties-window) **Olaylar** düğmesini kullanın.

**MFC ActiveX denetimi projenize bir olay eklemek için:**

1. Sınıf Görünümü, projedeki sınıfları göstermek için proje düğümünü genişletin.

1. Projenin denetim sınıfına sağ tıklayın.

1. Kısayol menüsünde, **Ekle**' yi seçin ve olay Ekle sihirbazını göstermek Için **olay Ekle** ' yi seçin.

1. Uygun sihirbaz kutularına olay bilgilerini sağlayın.

1. Olayı projeye eklemek için **son** ' u seçin.

## <a name="in-this-section"></a>Bu bölümde

- [Olay Ekleme Sihirbazı](#add-event-wizard)

## <a name="add-event-wizard"></a>Olay Ekleme Sihirbazı

Bu sihirbaz MFC ActiveX denetimi projesine bir olay ekler. Kendi olaylarınızı belirtebilir, tipik bir hisse senedi olayını özelleştirebilir veya stok olayları listesinden seçim yapabilirsiniz.

- **Olay adı**

   Otomasyon istemcileri tarafından sınıftan bir olay istemek için kullanılan adı ayarlar. Bir ad girin veya listeden birini seçin.

- **Olay türü**

   Eklenecek olay türünü gösterir. Yalnızca **olay adı** listesinden seçim yaparsanız kullanılabilir.

   |Seçenek|Açıklama|
   |------------|-----------------|
   |**Stok**|Bu sınıf için düğme tıklaması gibi bir stok olayının uygulanıp uygulanmayacak olduğunu belirtir. Hisse senedi olayları Microsoft Foundation Class (MFC) kitaplığı 'nda tanımlanmıştır.|
   |**Özel**|Kendi olay uygulamanızı kullandığınızı belirtir.|

- **İç ad**

   Olayı gönderen üye işlevinin adını ayarlar. Yalnızca özel olaylar için kullanılabilir. Ad, **olay adına** göre belirlenir. **Olay adından** farklı bir ad sağlamak istiyorsanız iç adı değiştirebilirsiniz.

- **Parametre türü**

   **Parametre adının** türünü ayarlar. Listeden türü seçin.

- **Parametre adı**

   Olaylarınızın içinden geçirilecek parametre adını ayarlar. Adı yazdıktan sonra, parametre listesini eklemek için **Ekle** ' yi seçmeniz gerekir.

   **Ekle**' yi seçtiğinizde parametre adı **parametre listesinde** görünür.

   > [!NOTE]
   > Bir parametre adı girip **Ekle**' yi seçmeden önce **son** ' u seçerseniz, parametre olaya eklenmez. Yöntemi bulmanız ve parametresini el ile eklemeniz gerekir.

- **Ekle**

   Parametre **adı**' nda belirttiğiniz parametreyi ve türünü **parametre listesine** ekler. Listeye bir parametre eklemek için **Ekle** ' yi seçin.

- **Kaldır**

   Listedeki **parametre listesinde** seçtiğiniz parametreyi kaldırır.

- **Parametre listesi**

   Yöntemi için şu anda eklenen tüm parametreleri ve türlerini görüntüler. Parametreleri eklerken, sihirbaz, **parametre listesini** her bir parametreyi türüyle görüntüleyecek şekilde güncelleştirir.
