---
description: 'Daha fazla bilgi edinin: ATL ekleme Iletişim kutusu'
title: ATL İletişim Kutusu Ekleme
ms.date: 11/04/2016
helpviewer_keywords:
- ATL projects, adding dialog resources
- MFC dialog boxes, ATL dialogs
- dialog boxes, ATL
ms.assetid: 152a378f-7b24-4f66-aeba-c740973f03a6
ms.openlocfilehash: 9d4abcafd5e12c6b8cffd636bf28a9e79f96e5ce
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165725"
---
# <a name="adding-an-atl-dialog-box"></a>ATL İletişim Kutusu Ekleme

Projenize ATL iletişim kutusu eklemek için projenizin atl desteği içeren bir ATL projesi ya da bir MFC projesi olması gerekir. Atl uygulaması oluşturmak için ATL [Proje Sihirbazı 'nı](../../atl/reference/atl-project-wizard.md) kullanabilir veya bir MFC UYGULAMASı için ATL desteği uygulamak üzere [MFC uygulamanıza ATL nesnesi ekleyebilirsiniz](../../mfc/reference/adding-atl-support-to-your-mfc-project.md) .

Varsayılan olarak, ATL Iletişim kutusu Sihirbazı, [Caxdialogimpl](../../atl/reference/caxdialogimpl-class.md)'den türetilmiş bir iletişim kutusu uygular. Bu sınıf, ActiveX ve Windows denetimlerini barındırmak için destek içerir. ActiveX denetim desteğinin ek yükünü istemiyorsanız, sihirbaz kodunuzu oluşturduktan sonra tüm örneklerini `CAxDialogImpl` [CSimpleDialog](../../atl/reference/csimpledialog-class.md) veya [cdialogimpl](../../atl/reference/cdialogimpl-class.md) ile temel sınıfınız olarak değiştirin.

> [!NOTE]
> `CSimpleDialog` yalnızca Windows ortak denetimlerini destekleyen kalıcı iletişim kutuları oluşturur. `CDialogImpl` kalıcı veya kalıcı olmayan iletişim kutuları oluşturur.

## <a name="to-add-an-atl-dialog-resource-to-your-project"></a>Projenize ATL iletişim kutusu kaynağı eklemek için

1. [Atl Proje Sihirbazı 'nı](../../atl/reference/atl-project-wizard.md)kullanarak bir ATL projesi oluşturun.

1. [Sınıf görünümü](/visualstudio/ide/viewing-the-structure-of-code), proje adına sağ tıklayın ve kısayol menüsünden **Ekle** ' ye tıklayın. **Sınıf Ekle**' ye tıklayın.

1. [Sınıf Ekle](../../ide/adding-a-class-visual-cpp.md#add-class-dialog-box) Iletişim kutusunun **Şablonlar** bölmesinde, **atl iletişim** kutusu ' na tıklayın. [ATL Iletişim sihirbazını](../../atl/reference/atl-dialog-wizard.md)göstermek için **Aç** ' a tıklayın.

Daha fazla bilgi için bkz. [bir Iletişim kutusu uygulama](../../atl/implementing-a-dialog-box.md).

## <a name="see-also"></a>Ayrıca bkz.

[Sınıf ekleme](../../ide/adding-a-class-visual-cpp.md)<br/>
[Pencere sınıfları](../../atl/atl-window-classes.md)<br/>
[İleti haritaları](../../atl/message-maps-atl.md)
