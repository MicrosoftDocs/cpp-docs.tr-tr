---
title: "Kalıcı olmayan özellik sayfası oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- modeless property sheets
- property sheets, modeless
- Create method [MFC], property sheets
ms.assetid: eafd8a92-cc67-4a69-a5fb-742c920d1ae8
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2e587c130a06ff30a38138f1e0ecf94e7cdfe1ad
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="creating-a-modeless-property-sheet"></a>Kalıcı Olmayan Özellik Sayfası Oluşturma
Normalde, oluşturduğunuz özellik sayfalarını kalıcı olur. Kalıcı özellik sayfası kullanırken, kullanıcının herhangi bir uygulamanın parçası kullanmadan önce özellik sayfasını kapatmalısınız. Bu makalede uygulamanın diğer bölümleri kullanırken özellik sayfası açık tutmak kullanıcıya izin veren bir kalıcı olmayan özellik sayfası oluşturmak için kullanabileceğiniz yöntemleri açıklar.  
  
 Kalıcı olmayan iletişim kutusu yerine bir modal iletişim kutusu olarak olarak bir özellik sayfasını görüntülemek için arama [CPropertySheet::Create](../mfc/reference/cpropertysheet-class.md#create) yerine [DoModal](../mfc/reference/cpropertysheet-class.md#domodal). Kalıcı olmayan özellik sayfası desteklemek için bazı ek görevler de uygulamanız gerekir.  
  
 Ek görevlerden birini özellik sayfasında ve özellik sayfası açık olduğunda değiştirme dış nesnesi arasında veri değiştiriyor. Bu, genellikle standart kalıcı olmayan iletişim kutuları için olduğu gibi aynı görevi içindir. Bu görev parçası kalıcı olmayan özellik sayfası ve özellik ayarları uygulandığı dış nesne arasındaki iletişim kanalı uygular. Bu uygulama öğesinden bir sınıf türetirseniz kadar kolaydır [CPropertySheet](../mfc/reference/cpropertysheet-class.md) kalıcı olmayan özellik sayfası için. Bu makalede, bunu yaptığınız varsayılmaktadır.  
  
 Kalıcı olmayan özellik sayfası ve dış iletişim için bir yöntem (örneğin bir görünüm geçerli seçim) nesnesidir dış nesne için özellik sayfasından bir işaretçi tanımlamak için. Bir işlev tanımlayın (aşağıdakine benzer olarak adlandırılan `SetMyExternalObject`) içinde `CPropertySheet`-türetilmiş sınıf odağı bir dış nesneden değiştiğinde işaretçinin değiştirin. `SetMyExternalObject` İşlevi yeni seçilen dış nesneyi yansıtmak için her özellik sayfası ayarlarını sıfırla gerekiyor. Bunu başarmak için `SetMyExternalObject` işlevi erişebilir olmalıdır [CPropertyPage](../mfc/reference/cpropertypage-class.md) ait nesneleri `CPropertySheet` sınıfı.  
  
 Özellik sayfaları bir özellik sayfası içinde erişim sağlamak için en uygun katıştırmak için yoludur `CPropertyPage` nesnelerini `CPropertySheet`-türetilmiş bir nesne içermelidir. Katıştırma `CPropertyPage` nesnelerini `CPropertySheet`-türetilen nesne farklı özellik sayfasını sahibi oluşturur, kalıcı iletişim kutuları için tipik Tasarım olarak `CPropertyPage` nesneleri ve özellik sayfası geçirir [ CPropertySheet::AddPage](../mfc/reference/cpropertysheet-class.md#addpage).  
  
 Kalıcı olmayan özellik sayfası ayarları için dış nesne zaman uygulanması gereken belirlemek için çok sayıda kullanıcı arabirimi seçenekleri vardır. Bir kullanıcının herhangi bir değer değiştiğinde geçerli özellik sayfası ayarları uygulamak için alternatiftir. Başka bir alternatif, dış nesnesine kaydetmeden önce değişiklikler özellik sayfalarındaki birikmesini olanak tanır. bir Uygula düğmesini sağlamaktır. Uygula düğmesini işleme için yollar hakkında daha fazla bilgi için bkz: [Uygula düğmesini işleme](../mfc/handling-the-apply-button.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özellik sayfaları](../mfc/property-sheets-mfc.md)   
 [Veri Değişimi](../mfc/exchanging-data.md)   
 [İletişim kutusunun yaşam döngüsü](../mfc/life-cycle-of-a-dialog-box.md)

