---
title: Olay İşleyici Sihirbazı
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.eventhandler.overview
helpviewer_keywords:
- Event Handler Wizard [C++]
ms.assetid: af8e1835-94b1-4d9a-b353-c519e011d3a1
ms.openlocfilehash: e48d995aed0c59cc4ba7b645706448b5c3618b4a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50654174"
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