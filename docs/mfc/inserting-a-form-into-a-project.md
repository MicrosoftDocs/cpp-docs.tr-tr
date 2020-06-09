---
title: Bir Projeye Form Ekleme
ms.date: 11/04/2016
helpviewer_keywords:
- inserting forms [MFC]
- Insert New dialog box [MFC]
- forms, adding to projects
ms.assetid: f3bd2998-3ce2-496d-ac5c-57ca70eec7cb
ms.openlocfilehash: 8e3162ac3917781920130bcbed23864eb90afa59
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84618426"
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
