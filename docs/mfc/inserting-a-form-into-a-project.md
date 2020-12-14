---
description: 'Hakkında daha fazla bilgi edinin: projeye form ekleme'
title: Bir Projeye Form Ekleme
ms.date: 11/04/2016
helpviewer_keywords:
- inserting forms [MFC]
- Insert New dialog box [MFC]
- forms, adding to projects
ms.assetid: f3bd2998-3ce2-496d-ac5c-57ca70eec7cb
ms.openlocfilehash: d0c67532261e4c5a5740f4ff07543f141b34d7a7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220493"
---
# <a name="inserting-a-form-into-a-project"></a>Bir Projeye Form Ekleme

Formlar, denetimler için uygun bir kapsayıcı sağlar. Uygulama MFC kitaplıklarını desteklediği sürece uygulamanıza kolayca MFC tabanlı bir form ekleyebilirsiniz.

### <a name="to-insert-a-form-into-your-project"></a>Projenize form eklemek için

1. Sınıf Görünümü, formunu eklemek istediğiniz projeyi seçin ve sağ fare düğmesine tıklayın.

1. Kısayol menüsünde, **Ekle** ' ye ve ardından **Sınıf Ekle**' ye tıklayın.

   **Yeni form** komutu kullanılamıyorsa, projeniz etkin şablon kitaplığı 'Nı (ATL) temel alabilir. ATL projesine form eklemek için, projeyi ilk oluştururken [belirli ayarları belirtmeniz](../atl/reference/application-settings-atl-project-wizard.md) gerekir.

1. **MFC** klasöründen **MFC sınıfı**' na tıklayın.

1. MFC sınıf Sihirbazı 'Nı kullanarak, yeni sınıfın [CFormView](reference/cformview-class.md)'dan türemesini sağlayın.

Visual C++, formu uygulamanıza ekler ve böylece denetim ekleme ve genel tasarımda çalışmaya başlayabilmeniz için Iletişim kutusu Düzenleyicisi içinde açılıyor.

Aşağıdaki ek adımları gerçekleştirmek isteyebilirsiniz (iletişim kutusu tabanlı uygulamalar için geçerli değildir):

1. `OnUpdate`Üye işlevini geçersiz kılın.

1. Görünüminizden belgenize veri taşımak için bir üye işlevi uygulayın.

1. `OnPrint`Üye işlevi oluşturun.

## <a name="see-also"></a>Ayrıca bkz.

[Form görünümleri](form-views-mfc.md)
