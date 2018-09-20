---
title: Ortak iletişim kutusu sınıfları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0a937ded9fe356627e36ad0262e749446553aa91
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46379729"
---
# <a name="common-dialog-classes"></a>Ortak İletişim Kutusu Sınıfları

Sınıf ek olarak [CDialog](../mfc/reference/cdialog-class.md), MFC sağlayan çeşitli sınıflar türetilen `CDialog` aşağıdaki tabloda gösterildiği gibi yaygın olarak kullanılan iletişim kutuları, kapsayan. Kapsüllenmiş iletişim kutuları "ortak iletişim kutusu" olarak adlandırılır ve Windows ortak iletişim kitaplığı (COMMDLG. bir parçasıdır DLL). İletişim şablonu kaynaklarına ve bu sınıflar için kod içinde Windows, Windows 3.1 ve sonraki sürümlerde bir parçası olan ortak iletişim kutuları sağlanır.

### <a name="common-dialog-classes"></a>Ortak İletişim Kutusu Sınıfları

|Türetilen bir iletişim kutusu sınıfı|Amaç|
|--------------------------|-------------|
|[CColorDialog](../mfc/reference/ccolordialog-class.md)|Kullanıcı Seç renkleri olanak tanır.|
|[CFileDialog](../mfc/reference/cfiledialog-class.md)|Kullanıcı Seç açmak veya kaydetmek için bir dosya adı sağlar.|
|[CFindReplaceDialog](../mfc/reference/cfindreplacedialog-class.md)|Bir bulma başlatır veya değiştir işlemini bir metin dosyasındaki kullanıcı sağlar.|
|[CFontDialog](../mfc/reference/cfontdialog-class.md)|Kullanıcının bir yazı tipi belirtmesine olanak tanır.|
|[CPrintDialog](../mfc/reference/cprintdialog-class.md)|Kullanıcının bir yazdırma işi için bilgileri belirtmesine olanak tanır.|
|[CPrintDialogEx](../mfc/reference/cprintdialogex-class.md)|Windows Print özellik sayfası.|

Tek tek sınıf adları ortak iletişim kutusu sınıfları hakkında daha fazla bilgi için bkz. *MFC başvurusu*. MFC OLE için kullanılan standart iletişim kutusu sınıfları sayısı da sağlar. Temel sınıfı, bu sınıfları hakkında daha fazla bilgi için bkz. [COleDialog](../mfc/reference/coledialog-class.md), *MFC başvurusu*.

MFC içinde üç sınıf iletişim gibi özelliklere sahiptir. Sınıfları hakkında daha fazla bilgi için [CFormView](../mfc/reference/cformview-class.md), [CRecordView](../mfc/reference/crecordview-class.md), ve [CDaoRecordView](../mfc/reference/cdaorecordview-class.md), sınıflara bakın *MFC başvurusu*. Sınıfı hakkında daha fazla bilgi için [CDialogBar](../mfc/reference/cdialogbar-class.md), bkz: [iletişim kutusu çubukları](../mfc/dialog-bars.md).

## <a name="see-also"></a>Ayrıca Bkz.

[İletişim Kutuları](../mfc/dialog-boxes.md)<br/>
[Bir İletişim Kutusunun Yaşam Döngüsü](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[OLE'deki İletişim Kutuları](../mfc/dialog-boxes-in-ole.md)

