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
ms.openlocfilehash: 544ce4cd0f4ed9a7f3592e5ec1691fb3734b8772
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "33340014"
---
# <a name="event-handler-wizard"></a>Olay İşleyici Sihirbazı
Bu sihirbaz, tercih ettiğiniz sınıfı için bir iletişim kutusu denetimi için bir olay işleyicisi ekler. Bir olay işleyiciden eklerseniz [Özellikler penceresini](/visualstudio/ide/reference/properties-window), iletişim kutusu uygulayan sınıfına ekleyin. Bkz: [iletişim kutusu denetimleri için olay işleyicileri ekleme](../windows/adding-event-handlers-for-dialog-box-controls.md) daha fazla bilgi için.  
  
 **Komut adı**  
 Olay işleyicisi eklenen Seçili denetimi tanımlar. Bu kutu kullanılamıyor.  
  
 **İleti türü**  
 Seçili denetimi için geçerli olası ileti işleyicileri listesini görüntüler.  
  
 **İşlev işleyicisi adı**  
 Olayını işlemek için eklenen işlevin adını görüntüler. Varsayılan olarak, ad ileti türü ve "Açık" $a komutu, temel alır. Örneğin, düğmesini adlı `IDC_BUTTON1`, ileti türü `BN_CLICKED` işlevi işleyici adını görüntüler `OnBnClickedButton1`.  
  
 **Sınıf listesi**  
 Olay işleyici ekleyebileceğiniz kullanılabilir sınıflarını görüntüler. Seçilen iletişim kutusu için sınıf kırmızı olarak görüntülenir.  
  
 **İşleyici açıklaması**  
 Seçili öğe için bir açıklama sağlar **ileti türü** kutusu. Bu kutu kullanılamıyor.  
  
 **Ekleme ve düzenleme**  
 Seçilen sınıf veya nesne ileti işleyicisi ekler ve denetim bildirim işleyici kodu ekleyebileceğiniz yeni işlev için Metin Düzenleyicisi'ni açar.  
  
 **Kod düzenleme**  
 Ekleme veya denetim bildirim işleyici kodu düzenleme için seçilen var işlevi için Metin Düzenleyicisi'ni açar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Olay işleyici ekleme](../ide/adding-an-event-handler-visual-cpp.md)