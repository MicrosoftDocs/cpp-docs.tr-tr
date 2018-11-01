---
title: Bir Projeye Form Ekleme
ms.date: 11/04/2016
helpviewer_keywords:
- inserting forms [MFC]
- Insert New dialog box [MFC]
- forms, adding to projects
ms.assetid: f3bd2998-3ce2-496d-ac5c-57ca70eec7cb
ms.openlocfilehash: 5f5758e84e89f23f06fb9d5f2fa97220d0279725
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50666628"
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

## <a name="see-also"></a>Ayrıca Bkz.

[Form görünümleri](../mfc/form-views-mfc.md)

