---
title: Bir projeye Form ekleme | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- inserting forms [MFC]
- Insert New dialog box [MFC]
- forms, adding to projects
ms.assetid: f3bd2998-3ce2-496d-ac5c-57ca70eec7cb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 968c24a4f64b88be6de95f0f1dd98c09eb494a97
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="inserting-a-form-into-a-project"></a>Bir Projeye Form Ekleme
Formları denetimleri için uygun bir kapsayıcı sağlar. MFC kitaplıkları uygulamasının desteklediği sürece, MFC tabanlı bir form uygulamanıza kolayca ekleyebilirsiniz.  
  
### <a name="to-insert-a-form-into-your-project"></a>Bir form projenize eklemek için  
  
1.  Sınıf Görünümü, formun eklemek istediğiniz projesini seçin ve farenin sağ düğmesiyle tıklatın.  
  
2.  Kısayol menüsünden tıklatın **Ekle** ve ardından **sınıfı Ekle**.  
  
     Varsa **yeni bir Form** komutu kullanılabilir değil, projenizi Etkin Şablon kitaplığı (ATL) üzerinde temel olabilir. Bir formu bir ATL projesine eklemek için şunları yapmanız gerekir [belirli ayarları belirtmek](../atl/reference/application-settings-atl-project-wizard.md) ilk proje oluşturulurken.  
  
3.  Gelen **MFC** klasörünü tıklatın **MFC sınıfı**.  
  
4.  MFC Sınıf Sihirbazı'nı kullanarak öğesinden türetilen yeni sınıfı hale [Cformview'yu](../mfc/reference/cformview-class.md).  
  
 Visual C++ ekler formun uygulamanıza, böylece başlamak için iletişim kutusu Düzenleyicisi içinde açma denetimleri ekleme ve genel tasarımını çalışma.  
  
 (İletişim tabanlı uygulamalar için geçerli değil) aşağıdaki ek adımları gerçekleştirmek isteyebilirsiniz:  
  
1.  Geçersiz kılma `OnUpdate` üye işlevi.  
  
2.  Verileri görünümünüzden belgenize taşımak için bir üye işlevini uygulayın.  
  
3.  Oluşturma bir `OnPrint` üye işlevi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Form görünümleri](../mfc/form-views-mfc.md)

