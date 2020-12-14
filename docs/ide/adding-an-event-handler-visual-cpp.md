---
description: 'Daha fazla bilgi edinin: olay işleyicisi ekleme'
title: Olay işleyicisi ekleme
ms.date: 11/12/2018
f1_keywords:
- vc.codewiz.eventhandler.overview
helpviewer_keywords:
- event handlers, adding
- properties [Visual Studio], MSBuild
- MSBuild, properties
- event handler wizard [C++]
ms.assetid: 050bebf0-a9e0-474b-905c-796fe5ac8fc3
ms.openlocfilehash: 0e65d25573b4e16d9815db289401251a6bb2d0f5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265538"
---
# <a name="add-an-event-handler"></a>Olay işleyicisi ekleme

Kaynak Düzenleyicisi ' nden, [olay işleyicisi Sihirbazı 'nı](#event-handler-wizard)kullanarak bir iletişim kutusu denetimi için yeni bir olay işleyicisi ekleyebilir veya var olan bir olay işleyicisini düzenleyebilirsiniz.

[Özellikler penceresi](/visualstudio/ide/reference/properties-window)kullanarak iletişim kutusunu uygulayan sınıfa bir olay ekleyebilirsiniz. Olayı iletişim kutusu sınıfından başka bir sınıfa eklemek için olay işleyicisi Sihirbazı ' nı kullanın.

**İletişim kutusu denetimine bir olay işleyicisi eklemek için:**

1. İletişim kutusu [düzenleyicisinde](../windows/dialog-editor.md)denetimi içeren iletişim kutusu kaynağını açmak için [kaynak görünümü](../windows/how-to-create-a-resource-script-file.md#create-resources) iletişim kutusu kaynağına çift tıklayın.

1. Bildirim olayını işlemek istediğiniz denetime sağ tıklayın.

1. Olay Işleyicisi Sihirbazı 'Nı göstermek için kısayol menüsünde **olay Işleyicisi Ekle** ' yi seçin.

1. **Sınıf liste** kutusunda seçilen sınıfa eklemek için **ileti türü** kutusundaki olayı seçin.

1. **İşlev işleyicisi ad** kutusunda varsayılan adı kabul edin veya istediğiniz adı belirtin.

1. Projeye olay işleyicisini eklemek için **Ekle ve Düzenle** ' yi seçin ve uygun olay işleyicisi kodunu eklemek için yeni işlevde metin düzenleyicisini açın.

   Seçilen ileti türünün seçili sınıf için zaten bir olay işleyicisi varsa, **ekleme ve düzenleme** kullanılamaz ve **kod düzenleme** kullanılabilir. Varolan işlevde metin düzenleyiciyi açmak için **kodu Düzenle** ' yi seçin.

Alternatif olarak, [Özellikler penceresi](/visualstudio/ide/reference/properties-window)olay işleyicileri ekleyebilirsiniz. Daha fazla bilgi için bkz. [iletişim kutusu denetimleri için olay Işleyicileri ekleme](../windows/adding-editing-or-deleting-controls.md).

## <a name="in-this-section"></a>Bu bölümde

- [Olay işleyicisi Sihirbazı](#event-handler-wizard)

## <a name="event-handler-wizard"></a>Olay işleyicisi Sihirbazı

Bu sihirbaz, seçtiğiniz sınıfa bir iletişim kutusu denetimi için bir olay işleyicisi ekler. [Özellikler penceresi](/visualstudio/ide/reference/properties-window)bir olay işleyicisi eklerseniz, bunu yalnızca iletişim kutusunu uygulayan sınıfa ekleyebilirsiniz. Daha fazla bilgi için bkz. [iletişim kutusu denetimleri için olay Işleyicileri ekleme](../windows/adding-editing-or-deleting-controls.md).

- **Komut adı**

  Olay işleyicisinin eklendiği Seçili denetimi tanımlar. Bu kutu kullanılamıyor.

- **Mesaj türü**

  Seçili denetim için geçerli olası ileti işleyicilerinin listesini görüntüler.

- **İşlev işleyicisi adı**

  Olayı işlemek için eklenen işlevin adını görüntüler. Ad varsayılan olarak ileti türüne ve komutuna göre, önüne göre belirlenir `On` . Örneğin, adlı düğme için `IDC_BUTTON1` , ileti türü `BN_CLICKED` işlev işleyicisi adını görüntüler `OnBnClickedButton1` .

- **Sınıf listesi**

  Bir olay işleyicisi ekleyebileceğiniz kullanılabilir sınıfları görüntüler. Seçili iletişim kutusu için sınıf kırmızı renkte görüntülenir.

- **İşleyici açıklaması**

  **İleti türü** kutusunda seçilen öğe için bir açıklama sağlar. Bu kutu kullanılamıyor.

- **Ekleme ve düzenleme**

  İleti işleyicisini seçili sınıfa veya nesneye ekler. Ayrıca, denetim bildirimine yönelik işleyici kodunu ekleyebilmeniz için metin düzenleyiciyi yeni işleve açar.

- **Kodu Düzenle**

  Denetim bildirim işleyicisi kodunu ekleyebileceğiniz veya düzenleyebilmeniz için seçili mevcut işleve metin düzenleyiciyi açar.
