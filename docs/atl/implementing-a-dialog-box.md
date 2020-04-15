---
title: İletişim Kutusu Uygulama
ms.date: 11/04/2016
helpviewer_keywords:
- CSimpleDialog class, implementing dialog boxes in ATL
- dialog boxes, ATL
- CAxDialogImpl class, implementing dialog boxes in ATL
- ATL, dialog boxes
ms.assetid: 478525f2-aa6a-435a-b162-68fc8aa98a8e
ms.openlocfilehash: 435926b0a0affde03580ceb2b479cb08a17d0454
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319482"
---
# <a name="implementing-a-dialog-box"></a>İletişim Kutusu Uygulama

ATL projenize iletişim kutusu eklemenin iki yolu vardır: ATL İletişim Sihirbazı'nı kullanın veya el ile ekleyin.

## <a name="adding-a-dialog-box-with-the-atl-dialog-wizard"></a>ATL İletişim Sihirbazı ile İletişim Kutusu Ekleme

Sınıf [Ekle iletişim kutusunda,](../ide/add-class-dialog-box.md)ATL projenize bir iletişim kutusu eklemek için ATL iletişim nesnesini seçin. Uygun şekilde ATL İletişim Sihirbazı'nı doldurun ve **Bitir'i**tıklatın. Sihirbaz, projenize [CAxDialogImpl'den](../atl/reference/caxdialogimpl-class.md) türetilen bir sınıf ekler. **Görünüm** menüsünden **Kaynak Görünümü'nü** açın, iletişim inizi bulun ve kaynak düzenleyicisinde açmak için çift tıklatın.

> [!NOTE]
> İletişim kutunuz `CAxDialogImpl`türetilmişse, hem ActiveX hem de Windows denetimlerini barındırabilir. İletişim kutusu sınıfınızda ActiveX denetim desteğinin ek yükü istemiyorsanız, bunun yerine [CSimpleDialog](../atl/reference/csimpledialog-class.md) veya [CDialogImpl'i](../atl/reference/cdialogimpl-class.md) kullanın.

İleti ve olay işleyicileri Sınıf Görünümü'nden iletişim sınıfınıza eklenebilir. Daha fazla bilgi için Bkz. [ATL İleti İmlası Ekleme.](../atl/adding-an-atl-message-handler.md)

## <a name="adding-a-dialog-box-manually"></a>El ile İletişim Kutusu Ekleme

İletişim kutusu uygulamak, pencere uygulamasına benzer. [CAxDialogImpl,](../atl/reference/caxdialogimpl-class.md) [CDialogImpl](../atl/reference/cdialogimpl-class.md)veya [CSimpleDialog'dan](../atl/reference/csimpledialog-class.md) bir sınıf türetin ve iletileri işlemek için bir [ileti eşlemi](../atl/message-maps-atl.md) beyan emz. Ancak, türemiş sınıfınızda bir iletişim şablonu kaynak kimliği de belirtmeniz gerekir. Sınıfınızın bu değeri tutmak `IDD` için çağrılan bir veri üyesi olması gerekir.

> [!NOTE]
> ATL İletişim Sihirbazı'nı kullanarak bir iletişim kutusu oluşturduğunuzda, sihirbaz üyeyi `IDD` otomatik olarak **enum** türüolarak ekler.

`CDialogImpl`Windows denetimlerini barındıran bir modal veya modeless iletişim kutusu uygulamanızı sağlar. `CAxDialogImpl`hem ActiveX hem de Windows denetimlerini barındıran bir modal veya modeless iletişim kutusu uygulamanızı sağlar.

Modal iletişim kutusu oluşturmak için, türetilmiş `CDialogImpl`(veya `CAxDialogImpl`türetilmiş) sınıfınızın bir örneğini oluşturun ve ardından [DoModal](../atl/reference/cdialogimpl-class.md#domodal) yöntemini arayın. Modal iletişim kutusunu kapatmak için, ileti işleyicisinden [EndDialog](../atl/reference/cdialogimpl-class.md#enddialog) yöntemini arayın. Modeless iletişim kutusu oluşturmak için, [Create](../atl/reference/cdialogimpl-class.md#create) `DoModal`'' yerine Oluştur yöntemini arayın. Modeless iletişim kutusunu yok etmek için [DestroyWindow'u](../atl/reference/cdialogimpl-class.md#destroywindow)arayın.

Batma olayları otomatik olarak [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md)yapılır. Türetilmiş bir `CWindowImpl`sınıftaki işleyicileri gibi iletişim kutusunun ileti işleyicilerini uygulayın. İletiye özgü bir iade değeri varsa, `LRESULT`iletiyi ' olarak döndürün. Döndürülen `LRESULT` değerler, Windows iletişim yöneticisi tarafından doğru işleme için ATL tarafından eşlenir. Ayrıntılar için, [CDialogImplBaseT::DialogProc](../atl/reference/cdialogimpl-class.md#dialogproc) in atlwin.h kaynak koduna bakın.

## <a name="example"></a>Örnek

Aşağıdaki sınıf bir iletişim kutusu uygular:

[!code-cpp[NVC_ATL_Windowing#66](../atl/codesnippet/cpp/implementing-a-dialog-box_1.h)]

## <a name="see-also"></a>Ayrıca bkz.

[Pencere Sınıfları](../atl/atl-window-classes.md)
