---
title: Olay işleyici Sihirbazı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.eventhandler.overview
dev_langs:
- C++
helpviewer_keywords:
- Event Handler Wizard [C++]
ms.assetid: af8e1835-94b1-4d9a-b353-c519e011d3a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4c2ff441fc38d460e27039d7825753a2011dac3e
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45702773"
---
# <a name="event-handler-wizard"></a>Olay İşleyici Sihirbazı
Bu sihirbaz, seçtiğiniz sınıfa bir iletişim kutusu denetimi için bir olay işleyicisi ekler. Bir olay işleyicisinden eklerseniz [Özellikler penceresi](/visualstudio/ide/reference/properties-window), iletişim kutusu uygulayan sınıfına ekleyin. Bkz: [iletişim kutusu denetimleri için olay işleyicileri ekleme](../windows/adding-event-handlers-for-dialog-box-controls.md) daha fazla bilgi için.  
  
- **Komut adı**

   Kendisi için olay işleyicisi eklenir, seçilen denetimi tanımlar. Bu kutuyu kullanılamıyor.  
  
- **İleti türü**

   Seçili denetim için geçerli olası ileti işleyicileri listesini görüntüler.  
  
- **İşlev işleyicisi adı**

   Olayı işlemek için eklenen işlev adını görüntüler. Varsayılan olarak, ileti türü ve "Açık" başına, komut adı temel alır. Örneğin, düğme için adlı `IDC_BUTTON1`, ileti türü `BN_CLICKED` işlev işleyicisi adı görüntüler `OnBnClickedButton1`.  
  
- **Sınıf listesi**

   Bir olay işleyicisi ekleyebileceğiniz kullanılabilir sınıflarını görüntüler. Seçili iletişim kutusu sınıfı kırmızı renkte görüntülenir.  
  
- **İşleyici açıklaması**

   Seçili öğe için bir açıklama sağlar **ileti türü** kutusu. Bu kutuyu kullanılamıyor.  
  
- **Ekleme ve düzenleme**

   Seçilen bir sınıf veya nesne için ileti işleyicisi ekler ve sonra Denetim bildirimi işleyicinizin kodunu ekleyebilmek yeni işleve Metin Düzenleyicisi'ni açar.  
  
- **Kodu düzenleme**

   Ekleme ya da Denetim bildirimi işleyicinizin kodunu düzenle seçili mevcut işlevi metin düzenleyicisi açılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Olay işleyici ekleme](../ide/adding-an-event-handler-visual-cpp.md)