---
title: Bir olay işleyicisi ekleme
ms.date: 11/12/2018
f1_keywords:
- vc.codewiz.eventhandler.overview
- vc.codewiz.eventhandler.overview
helpviewer_keywords:
- event handlers, adding
- properties [Visual Studio], MSBuild
- MSBuild, properties
- event handler wizard [C++]
ms.assetid: 050bebf0-a9e0-474b-905c-796fe5ac8fc3
ms.openlocfilehash: 96e5b8777bb8b0c976277a06e8ad49b3334921fb
ms.sourcegitcommit: c1f646c8b72f330fa8cf5ddb0f8f261ba10d16f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2019
ms.locfileid: "58328577"
---
# <a name="add-an-event-handler"></a>Bir olay işleyicisi ekleme

Kaynak Düzenleyicisi'nde, yeni bir olay işleyicisi ekleyebilir, veya Düzenle iletişim kutusu denetimi kullanarak var olan olay işleyicisi, [olay işleyici Sihirbazı](#event-handler-wizard).

İletişim kutusunu kullanarak uygulama sınıfa olaya ekleyebilirsiniz [Özellikler penceresi](/visualstudio/ide/reference/properties-window). Olay iletişim kutusu sınıf dışında bir sınıf eklemek için olay işleyici Sihirbazı'nı kullanın.

**Bir iletişim kutusu denetimi olay işleyicisi eklemek için:**

1. İletişim kutusu kaynak çift [kaynak görünümü](../windows/how-to-create-a-resource-script-file.md#create-resources) denetimi içeren bir iletişim kutusu kaynağına açmak için [iletişim kutusu Düzenleyicisi](../windows/dialog-editor.md).

1. Bildirim olayı işlemek istediğiniz denetime sağ tıklayın.

1. Kısayol menüsünde **olay işleyici Ekle** olay işleyici Sihirbazı'nı görüntülemek için.

1. Olay seçin **ileti türü** de seçilen sınıfı eklemek için onay kutusunu **sınıf listesi** kutusu.

1. Varsayılan adı kabul **işlev işleyicisi adı** kutusuna veya tercih ettiğiniz bir ad sağlayın.

1. Seçin **ekleme ve düzenleme** projeye olay işleyicisi eklemek ve uygun bir olay işleyici kodu eklemek için yeni işlevi metin düzenleyicisini açın.

   Seçili ileti türü seçilen bir sınıf için bir olay işleyicisi zaten varsa **ekleme ve düzenleme** kullanılamıyor ve **kod düzenleme** kullanılabilir. Seçin **kod düzenleme** mevcut işlevi metin düzenleyiciyi açın.

Alternatif olarak, olay işleyicilerindeki ekleyebilirsiniz [Özellikler penceresi](/visualstudio/ide/reference/properties-window). Daha fazla bilgi için [iletişim kutusu denetimleri için olay işleyicileri ekleme](../windows/adding-event-handlers-for-dialog-box-controls.md).

## <a name="in-this-section"></a>Bu bölümde

- [Olay işleyici Sihirbazı](#event-handler-wizard)

## <a name="event-handler-wizard"></a>Olay işleyici Sihirbazı

Bu sihirbaz, seçtiğiniz sınıfa bir iletişim kutusu denetimi için bir olay işleyicisi ekler. Bir olay işleyicisinden eklerseniz [Özellikler penceresi](/visualstudio/ide/reference/properties-window), iletişim kutusu uygulayan sınıfına ekleyin. Daha fazla bilgi için [iletişim kutusu denetimleri için olay işleyicileri ekleme](../windows/adding-event-handlers-for-dialog-box-controls.md).

- **Komut adı**

  Kendisi için olay işleyicisi eklenir, seçilen denetimi tanımlar. Bu kutuyu kullanılamıyor.

- **İleti türü**

  Seçili denetim için geçerli olası ileti işleyicileri listesini görüntüler.

- **İşlev işleyicisi adı**

  Olayı işlemek için eklenen işlev adını görüntüler. İleti türü ve tarafından başına, komut, varsayılan olarak adı dayanır `On`. Örneğin, düğme için adlı `IDC_BUTTON1`, ileti türü `BN_CLICKED` işlev işleyicisi adı görüntüler `OnBnClickedButton1`.

- **Sınıf listesi**

  Bir olay işleyicisi ekleyebileceğiniz kullanılabilir sınıflarını görüntüler. Seçili iletişim kutusu sınıfı kırmızı renkte görüntülenir.

- **İşleyici açıklaması**

  Seçili öğe için bir açıklama sağlar **ileti türü** kutusu. Bu kutuyu kullanılamıyor.

- **Ekleme ve düzenleme**

  Seçilen bir sınıf veya nesne için ileti işleyicisi ekler. Denetim bildirimi işleyicinizin kodunu ekleyebilmeniz için de yeni işleve metin düzenleyicisi açılır.

- **Kodu düzenleme**

  Ekleme ya da Denetim bildirimi işleyicinizin kodunu düzenle seçili mevcut işlevi metin düzenleyicisi açılır.
