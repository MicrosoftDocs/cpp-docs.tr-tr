---
title: Bir Projeye Form Ekleme
ms.date: 11/04/2016
helpviewer_keywords:
- inserting forms [MFC]
- Insert New dialog box [MFC]
- forms, adding to projects
ms.assetid: f3bd2998-3ce2-496d-ac5c-57ca70eec7cb
ms.openlocfilehash: 2fa344f2d84b39be4ee36fd845edb82c14b6c519
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57286536"
---
# <a name="inserting-a-form-into-a-project"></a>Bir Projeye Form Ekleme

Formları denetimleri için uygun bir kapsayıcı sağlar. MFC kitaplıkları uygulamanın desteklediği sürece, MFC tabanlı bir form uygulamanıza kolayca ekleyebilirsiniz.

### <a name="to-insert-a-form-into-your-project"></a>Bir form projenize eklemek için

1. Sınıf Görünümü formu eklemek istediğiniz projeyi seçin ve sağ fare düğmesine tıklayın.

1. Kısayol menüsünden tıklayın **Ekle** ve ardından **sınıfı Ekle**.

   Varsa **yeni formu** komut kullanılabilir değil, projenizin etkin Şablon kitaplığı (ATL) üzerinde temel alıyor olabilir. Bir form bir ATL projesine eklemek için şunları yapmanız gerekir [belirli ayarları belirtin](../atl/reference/application-settings-atl-project-wizard.md) projeyi oluştururken ilk.

1. Gelen **MFC** klasörünü tıklatın **MFC sınıfı**.

1. MFC Sınıf Sihirbazı'nı kullanarak yeni bir sınıf türetin olun [CFormView](../mfc/reference/cformview-class.md).

Visual C++ ekler form uygulamanıza, böylece siz içinde iletişim kutusu düzenleyicisini açmadan denetimler ekleme ve genel tasarımını çalışma.

(İletişim kutusu tabanlı uygulamalar için geçerli değildir) aşağıdaki ek adımları gerçekleştirmek isteyebilirsiniz:

1. Geçersiz kılma `OnUpdate` üye işlevi.

1. Belgenize görünümünüzden verileri taşımak için bir üye işlevi uygulayın.

1. Oluşturma bir `OnPrint` üye işlevi.

## <a name="see-also"></a>Ayrıca bkz.

[Form görünümleri](../mfc/form-views-mfc.md)
