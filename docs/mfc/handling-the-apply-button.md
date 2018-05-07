---
title: Uygula düğmesini işleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Apply button in property sheet
- property sheets, Apply button
ms.assetid: 7e977015-59b8-406f-b545-aad0bfd8d55b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d80dc3d02a7530ee54c9ff26cd0a03465bd77cdd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="handling-the-apply-button"></a>Uygula Düğmesini İşleme
Özellik sayfaları standart iletişim kutuları bulunmayan bir özelliği vardır: yapmış özellik sayfasını kapatmadan önce değişiklikleri uygulamak kullanıcı sağlarlar. Bu yapılır Uygula düğmesini kullanarak. Bu makalede, bu özelliği düzgün bir şekilde uygulamak için kullanabileceğiniz yöntemler açıklanmaktadır.  
  
 Kullanıcı iletişim kutusunu kapatmak için Tamam'ı tıklattığında kalıcı iletişim kutuları için dış nesne genellikle ayarlarını uygular. Aynı özellik sayfası için geçerlidir: kullanıcı Tamam tıkladığında, özellik sayfasında yeni ayarlar geçerli olur.  
  
 Ancak, özellik sayfası iletişim kutusunu kapatmak zorunda kalmadan ayarlarını kaydetmek kullanıcı izin vermek isteyebilirsiniz. Uygula düğmesini işlevi budur. Uygula düğmesini yalnızca geçerli ayarları şu anda etkin sayfanın uygulama aksine dış nesnenin özellik sayfaları tümünde geçerli ayarlarını uygular.  
  
 Varsayılan olarak, her zaman Uygula düğmesi devre dışıdır. Uygula düğmesini uygun zamanlarda etkinleştirmek için kod yazmanız gerekir ve aşağıda açıklandığı gibi Uygula etkisini uygulamak için kod yazmanız gerekir.  
  
 Kullanıcıya Uygula işlevselliğini sunmaya istemiyorsanız Uygula düğmesini kaldırmak gerekli değildir. Standart özellik sayfası desteği gelecekteki Windows sürümlerinde kullanılabilir kullanan uygulamalar arasında genel olarak, devre dışı bırakabilirsiniz.  
  
 Değiştirilen olarak bir sayfa rapor ve Uygula düğmesini etkinleştirmek için arama **CPropertyPage::SetModified (TRUE)**. Varsa değiştirilen sayfaları rapor Uygula düğmesini, olup şu anda etkin sayfa değiştirildi bağımsız olarak, etkin kalır.  
  
 Çağırmalısınız [CPropertyPage::SetModified](../mfc/reference/cpropertypage-class.md#setmodified) her kullanıcı sayfasında tüm ayarlarını değiştirir. Bir kullanıcı bir sayfasında ayarını değiştirdiğinde belirlemek için bir yoldur gibi değişikliği bildirim işleyicileri her özellik sayfası denetimlerinde uygulamak için **EN_CHANGE** veya **BN_CLICKED**.  
  
 Uygula düğmesini etkisini uygulamak için özellik sayfasını, sahibi ya da başka bir dış nesnenin özellik sayfaları geçerli ayarları uygulamak için bu uygulamada bildirmeniz gerekir. Aynı anda özellik sayfasında Uygula düğmesini çağırarak devre dışı bırakmanız gerekir **CPropertyPage::SetModified (FALSE)** dış nesne kendi değişiklikler uygulanan tüm sayfalar için.  
  
 MFC genel örnek bu işlem bir örnek için bkz [PROPDLG](../visual-cpp-samples.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özellik sayfaları](../mfc/property-sheets-mfc.md)

