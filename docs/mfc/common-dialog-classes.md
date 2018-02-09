---
title: "Ortak iletişim kutusu sınıfları | Microsoft Docs"
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
- dialog classes [MFC]
- dialog boxes [MFC], Windows common dialogs
- common dialog boxes [MFC], common dialog classes
- common dialog classes [MFC]
- MFC dialog boxes [MFC], Windows common dialogs
- Windows common dialogs [MFC]
- dialog classes [MFC], common
- common dialog boxes [MFC]
ms.assetid: 5c4f6443-896c-4b05-a7df-8169fdadc71d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d76c387c9aa9f53f8503d3606b2b47cdb5c6be6d
ms.sourcegitcommit: a5916b48541f804a79891ff04e246628b5f9a24a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="common-dialog-classes"></a>Ortak İletişim Kutusu Sınıfları
Sınıf yanı sıra [CDialog](../mfc/reference/cdialog-class.md), MFC kaynakları türetilen birden fazla sınıf `CDialog` aşağıdaki tabloda gösterildiği gibi yaygın olarak kullanılan iletişim kutularını kapsayan. Kapsüllenmiş iletişim kutularında "ortak iletişim kutuları" olarak adlandırılır ve Windows ortak iletişim kitaplığı (COMMDLG. parçası DLL). İletişim şablonu kaynakları ve bu sınıflar için kod Windows'da Windows 3.1 ve sonraki sürümleri parçası olan ortak iletişim kutuları sağlanır.  
  
### <a name="common-dialog-classes"></a>Ortak İletişim Kutusu Sınıfları  
  
|Türetilen iletişim kutusu sınıfı|Amaç|  
|--------------------------|-------------|  
|[CColorDialog](../mfc/reference/ccolordialog-class.md)|Kullanıcı Seç renkleri olanak sağlar.|  
|[CFileDialog](../mfc/reference/cfiledialog-class.md)|Kullanıcı açmak veya kaydetmek için bir dosya adı Seç olanak sağlar.|  
|[CFindReplaceDialog](../mfc/reference/cfindreplacedialog-class.md)|Kullanıcının bir bulma başlatmak veya bir metin dosyasındaki işlemi değiştirmenize izin verir.|  
|[CFontDialog](../mfc/reference/cfontdialog-class.md)|Kullanıcının bir yazı tipi belirtmesine olanak tanır.|  
|[CPrintDialog](../mfc/reference/cprintdialog-class.md)|Kullanıcının bir yazdırma işi için bilgileri belirtmesine olanak tanır.|  
|[CPrintDialogEx](../mfc/reference/cprintdialogex-class.md)|Windows yazdırma özellik sayfası.|  
  
 Ortak iletişim kutusu sınıfları hakkında daha fazla bilgi için tek tek sınıf adlarının bkz *MFC başvurusu*. MFC OLE için kullanılan standart iletişim kutusu sınıfları sayısı da sağlar. Taban sınıfı bu sınıfları hakkında daha fazla bilgi için bkz: [COleDialog](../mfc/reference/coledialog-class.md), *MFC başvurusu*.  
  
 MFC içinde üç diğer sınıflar iletişim benzer özelliklere sahip. Sınıfları hakkında bilgi için [Cformview'yu](../mfc/reference/cformview-class.md), [CRecordView](../mfc/reference/crecordview-class.md), ve [CDaoRecordView](../mfc/reference/cdaorecordview-class.md), sınıflara bakın *MFC başvurusu*. Sınıfı hakkında bilgi için [CDialogBar](../mfc/reference/cdialogbar-class.md), bkz: [iletişim kutusu çubukları](../mfc/dialog-bars.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İletişim kutuları](../mfc/dialog-boxes.md)   
 [İletişim kutusunun yaşam döngüsü](../mfc/life-cycle-of-a-dialog-box.md)   
 [OLE'deki İletişim Kutuları](../mfc/dialog-boxes-in-ole.md)

