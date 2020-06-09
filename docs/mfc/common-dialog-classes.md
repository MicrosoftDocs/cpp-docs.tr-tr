---
title: Ortak İletişim Kutusu Sınıfları
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
ms.openlocfilehash: 2efe095a6d5b71321cbbe56fdee662509baa4573
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619032"
---
# <a name="common-dialog-classes"></a>Ortak İletişim Kutusu Sınıfları

MFC, [CDialog](reference/cdialog-class.md)sınıfına ek olarak, `CDialog` Aşağıdaki tabloda gösterildiği gibi yaygın olarak kullanılan iletişim kutularını kapsülleyen çeşitli sınıflar sağlar. Kapsüllenen iletişim kutuları "ortak iletişim kutuları" olarak adlandırılır ve Windows ortak iletişim kutusu kitaplığının (COMMDLG) bir parçasıdır. DLL). Bu sınıfların iletişim kutusu-şablon kaynakları ve kodu, Windows sürümleri 3,1 ve üzeri bir parçası olan Windows ortak iletişim kutularında verilmiştir.

### <a name="common-dialog-classes"></a>Ortak İletişim Kutusu Sınıfları

|Türetilmiş iletişim kutusu sınıfı|Amaç|
|--------------------------|-------------|
|[CColorDialog](reference/ccolordialog-class.md)|Kullanıcının renk seçmesini sağlar.|
|[CFileDialog](reference/cfiledialog-class.md)|Kullanıcının açılacak veya kaydedilecek bir dosya adı seçmesini sağlar.|
|[CFindReplaceDialog](reference/cfindreplacedialog-class.md)|Kullanıcının bir metin dosyasında bulma veya değiştirme işlemi başlatmasını sağlar.|
|[CFontDialog](reference/cfontdialog-class.md)|Kullanıcının bir yazı tipi belirtmesini sağlar.|
|[CPrintDialog](reference/cprintdialog-class.md)|Kullanıcının bir yazdırma işi için bilgi belirtmesini sağlar.|
|[CPrintDialogEx](reference/cprintdialogex-class.md)|Windows yazdırma özelliği sayfası.|

Ortak iletişim kutusu sınıfları hakkında daha fazla bilgi için *MFC başvurusunda*ayrı sınıf adlarına bakın. MFC Ayrıca OLE için kullanılan bir dizi standart iletişim kutusu sınıfı sağlar. Bu sınıflar hakkında daha fazla bilgi için, *MFC başvurusu*içindeki temel sınıf, [Colet iletişim kutusu](reference/coledialog-class.md)' na bakın.

MFC 'deki üç diğer sınıfın iletişim benzeri özellikleri vardır. [CFormView](reference/cformview-class.md), [CRecordView](reference/crecordview-class.md)ve [CDaoRecordView](reference/cdaorecordview-class.md)sınıfları hakkında daha fazla bilgi için *MFC başvurusu*içindeki sınıflara bakın. Sınıf [CDialogBar](reference/cdialogbar-class.md)hakkında daha fazla bilgi için bkz. [İletişim çubukları](dialog-bars.md).

## <a name="see-also"></a>Ayrıca bkz.

[İletişim Kutuları](dialog-boxes.md)<br/>
[MFC’de İletişim Kutularıyla çalışma](life-cycle-of-a-dialog-box.md)<br/>
[OLE 'deki iletişim kutuları](dialog-boxes-in-ole.md)
