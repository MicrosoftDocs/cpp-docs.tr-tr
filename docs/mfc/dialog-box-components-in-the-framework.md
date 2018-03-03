---
title: "Framework'te iletişim kutusu bileşenleri | Microsoft Docs"
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
- MFC dialog boxes [MFC], creating
- dialog classes [MFC], dialog box components
- MFC dialog boxes [MFC], about MFC dialog boxes
- dialog templates [MFC], MFC framework
- MFC dialog boxes [MFC], dialog resource
ms.assetid: 592db160-0a8a-49be-ac72-ead278aca53f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 840e66def6a908b26b5021537eddee68c50a9628
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="dialog-box-components-in-the-framework"></a>Framework'te İletişim Kutusu Bileşenleri
MFC çerçevesi bir iletişim kutusu iki bileşenden oluşur:  
  
-   İletişim kutusunun denetimleri ve yatırımlarından belirten bir iletişim şablon kaynağı.  
  
     İletişim kaynağını içinden Windows iletişim kutusu penceresinin oluşturur ve görüntüler bir iletişim şablonunu depolar. Şablon boyutuna, konum, stil ve türleri ve iletişim kutusunun denetimleri konumlarını dahil olmak üzere, iletişim kutusunun özellikleri belirtir. Genellikle bir kaynak olarak saklanan bir iletişim şablonunu kullanır, ancak, aynı zamanda bellekte kendi şablonunuzu oluşturabilirsiniz.  
  
-   Bir iletişim kutusu sınıfı türetilen [CDialog](../mfc/reference/cdialog-class.md), iletişim kutusu yönetmek için programlı bir arabirim sağlar.  
  
     Bir iletişim kutusu bir penceredir ve bir Windows pencere görünür olduğunda bağlı. İletişim penceresi oluşturulduğunda, iletişim şablon kaynağı alt iletişim kutusu için pencere denetimleri oluşturmak için şablon olarak kullanılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İletişim kutuları](../mfc/dialog-boxes.md)   
 [Bir İletişim Kutusunun Yaşam Döngüsü](../mfc/life-cycle-of-a-dialog-box.md)

