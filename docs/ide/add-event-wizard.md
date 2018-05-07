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
ms.openlocfilehash: f92f871f22fb01f3f0f37677c393fcd481c08120
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="add-event-wizard"></a>Olay Ekleme Sihirbazı
Bu sihirbaz, bir olay bir MFC ActiveX denetimi projesine ekler. Stok olayları listesinden seçebilirsiniz veya genellikle stok olay özelleştirebilirsiniz veya kendi olay belirtebilirsiniz.  
  
 **Olay adı**  
 Sınıfından bir olay istemek için Otomasyon istemcileri tarafından kullanılan adını ayarlar. Bir ad girin veya listeden birini seçin.  
  
 **Olay türü**  
 Eklenecek olay türünü belirtir. Yalnızca menüden seçerseniz kullanılabilir **olay adı** listesi.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**Hisse senedi**|Bir düğmeye gibi bir stok olayı Bu sınıf için uygulanacak belirtir. Stok olayları Microsoft Foundation Class (MFC) Kitaplığı'nda tanımlanır.|  
|**Özel**|Olayın kendi uygulama sağlama belirtir.|  
  
 **İç adı**  
 Olay gönderir üye işlevin adını ayarlar. Yalnızca özel olaylar için kullanılabilir. Ad temel **olay adı**. Farklı bir ad sağlamak istiyorsanız iç adını değiştirebilirsiniz **olay adı**.  
  
 **Parametre türü**  
 Türü için ayarlar **parametre adı**. Listeden seçin.  
  
 **Parametre adı**  
 Olayınızın iletmek için bir parametre adını ayarlar. Adını yazdıktan sonra'ı tıklatmalısınız **Ekle** parametreleri listesine eklemek için.  
  
 Tıkladığınızda **Ekle**, parametre adı görünür **parametre listesi**.  
  
> [!NOTE]
>  Bir parametre adı sağlayın ve ardından **son** tıklamadan önce **Ekle**, parametre olaya eklenmez sonra. Find yöntemi ve parametre el ile ekleyin. **Parametre listesi**  
  
 **Ekle**  
 Belirttiğiniz parametre ekler **parametre adı**ve kendi türü için **parametre listesi**. ' I tıklatmalısınız **Ekle** bir parametre listesine eklemek için.  
  
 **Kaldır**  
 Öğesinde parametre kaldırır **parametre listesi** listeden.  
  
 **Parametre listesi**  
 Tüm parametreleri ve şu anda yöntemi için eklenen türlerini görüntüler. Parametre ekleme gibi sihirbaz güncelleştirir **parametre listesi** her parametre türü ile görüntülemek için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Olay ekleme](../ide/adding-an-event-visual-cpp.md)