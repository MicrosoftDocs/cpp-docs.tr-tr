---
title: Ortak Iletişim kutusu sınıfları
ms.date: 11/04/2016
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
ms.openlocfilehash: d11d0978763d9599b0471a8e994f15a267f7cb8f
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685553"
---
# <a name="common-dialog-classes"></a>Ortak Iletişim kutusu sınıfları

MFC, [CDialog](../mfc/reference/cdialog-class.md)sınıfına ek olarak, aşağıdaki tabloda gösterildiği gibi yaygın olarak kullanılan iletişim kutularını kapsülleyen `CDialog` ' den türetilmiş çeşitli sınıflar sağlar. Kapsüllenen iletişim kutuları "ortak iletişim kutuları" olarak adlandırılır ve Windows ortak iletişim kutusu kitaplığının (COMMDLG) bir parçasıdır. DLL). Bu sınıfların iletişim kutusu-şablon kaynakları ve kodu, Windows sürümleri 3,1 ve üzeri bir parçası olan Windows ortak iletişim kutularında verilmiştir.

### <a name="common-dialog-classes"></a>Ortak Iletişim kutusu sınıfları

|Türetilmiş iletişim kutusu sınıfı|Amaç|
|--------------------------|-------------|
|[CColorDialog](../mfc/reference/ccolordialog-class.md)|Kullanıcının renk seçmesini sağlar.|
|[CFileDialog](../mfc/reference/cfiledialog-class.md)|Kullanıcının açılacak veya kaydedilecek bir dosya adı seçmesini sağlar.|
|[CFindReplaceDialog](../mfc/reference/cfindreplacedialog-class.md)|Kullanıcının bir metin dosyasında bulma veya değiştirme işlemi başlatmasını sağlar.|
|[CFontDialog](../mfc/reference/cfontdialog-class.md)|Kullanıcının bir yazı tipi belirtmesini sağlar.|
|[CPrintDialog](../mfc/reference/cprintdialog-class.md)|Kullanıcının bir yazdırma işi için bilgi belirtmesini sağlar.|
|[CPrintDialogEx](../mfc/reference/cprintdialogex-class.md)|Windows yazdırma özelliği sayfası.|

Ortak iletişim kutusu sınıfları hakkında daha fazla bilgi için *MFC başvurusunda*ayrı sınıf adlarına bakın. MFC Ayrıca OLE için kullanılan bir dizi standart iletişim kutusu sınıfı sağlar. Bu sınıflar hakkında daha fazla bilgi için, *MFC başvurusu*içindeki temel sınıf, [Colet iletişim kutusu](../mfc/reference/coledialog-class.md)' na bakın.

MFC 'deki üç diğer sınıfın iletişim benzeri özellikleri vardır. [CFormView](../mfc/reference/cformview-class.md), [CRecordView](../mfc/reference/crecordview-class.md)ve [CDaoRecordView](../mfc/reference/cdaorecordview-class.md)sınıfları hakkında daha fazla bilgi için *MFC başvurusu*içindeki sınıflara bakın. Sınıf [CDialogBar](../mfc/reference/cdialogbar-class.md)hakkında daha fazla bilgi için bkz. [İletişim çubukları](../mfc/dialog-bars.md).

## <a name="see-also"></a>Ayrıca bkz.

[İletişim kutuları](../mfc/dialog-boxes.md)<br/>
[MFC 'de Iletişim kutularıyla çalışma](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[OLE 'deki iletişim kutuları](../mfc/dialog-boxes-in-ole.md)
