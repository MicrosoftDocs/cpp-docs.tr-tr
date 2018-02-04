---
title: "Sınıf (Visual C++) ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.codewiz.classes.adding
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding classes
- classes [C++], creating
- classes [C++], adding
ms.assetid: c34b5f70-4e72-4faa-ba21-e2b05361c4d9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ac87368f2bd38c32425799103fa3999dd11b3298
ms.sourcegitcommit: 30ab99c775d99371ed22d1a46598e542012ed8c6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/03/2018
---
# <a name="adding-a-class-visual-c"></a>Sınıf Ekleme (Visual C++)
Visual C++ projesinde bir sınıf eklemek için **Çözüm Gezgini**, projeye sağ tıklayın, **Ekle**ve ardından **sınıfı**. Bu açılır [Ekle iletişim kutusu sınıfı](../ide/add-class-dialog-box.md) iletişim kutusu.  
  
 Bir sınıf eklediğinizde, MFC veya ATL zaten sınıflardan farklı bir ad belirtmelisiniz Her iki Kitaplığı'nda zaten bir adı belirtirseniz, IDE bir hata iletisi gösterir.  
  
 Adlandırma kuralını, projenizin varolan bir ad kullanmanızı gerektiriyorsa, C++ büyük/küçük harfe duyarlıdır çünkü daha sonra yalnızca harflerin bir veya daha fazla adında değiştirebilirsiniz. Örneğin, bir sınıf adlandıramazsınız rağmen `CDocument`, adı verebilirsiniz `cdocument`.  
  
## <a name="what-kind-of-class-do-you-want-to-add"></a>Ne tür bir sınıf eklemek istiyor musunuz?  
 İçinde **sınıfı Ekle** 'nı iletişim kutusu, **Visual C++** yüklenmiş şablonlar birkaç gruplandırmaları görüntülenir sol bölmedeki düğüm. Grupları Ekle **CLR**, **ATL**, **MFC**, ve **C++**. Bir grup seçtiğinizde, o gruptaki kullanılabilir şablonların listesini Orta bölmede görüntülenir. Her bir şablon sınıfı için gerekli olan kaynak kodu ve dosyaları içerir.  
  
 Yeni bir sınıf oluşturmak için Orta bölmede bir şablon seçin, sınıf için bir ad yazın **adı** ve'ı tıklatın **Ekle**. Bu açılır **sınıf Ekleme Sihirbazı'nı** böylece sınıfı için seçenekleri belirleyebilirsiniz.  
  
-   MFC sınıfları oluşturma hakkında daha fazla bilgi için bkz: [MFC sınıfı](../mfc/reference/adding-an-mfc-class.md).  
  
-   ATL sınıfları oluşturma hakkında daha fazla bilgi için bkz: [ATL Basit Nesne](../atl/reference/adding-an-atl-simple-object.md).  
  
> [!NOTE]
>  Şablon **MFC ATL desteği ekleme** bir sınıf oluşturmaz, ancak bunun yerine ATL kullanmak için proje yapılandırır Daha fazla bilgi için bkz: [MFC projesinde ATL desteği](../mfc/reference/adding-atl-support-to-your-mfc-project.md).  
  
 MFC, ATL veya CLR kullanmayan bir C++ sınıf yapma **C++ sınıfı** şablonunda **C++** grubuna yüklenmiş şablonlar. Daha fazla bilgi için bkz: [genel C++ sınıfı ekleme](../ide/adding-a-generic-cpp-class.md).  
  
 C++ sınıfları form tabanlı iki tür mevcuttur. İlki [Cformview'yu sınıfı](../mfc/reference/cformview-class.md) bir MFC sınıfı oluşturur. İkinci bir CLR Windows Forms sınıfı oluşturur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir form tabanlı MFC uygulaması oluşturma](../mfc/reference/creating-a-forms-based-mfc-application.md)   
 [Sınıf Ekle iletişim kutusu](../ide/add-class-dialog-box.md)   
 [Uygulama sihirbazları kullanarak masaüstü projeleri oluşturma](../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Kod sihirbazlarıyla işlevsellik ekleme](../ide/adding-functionality-with-code-wizards-cpp.md)