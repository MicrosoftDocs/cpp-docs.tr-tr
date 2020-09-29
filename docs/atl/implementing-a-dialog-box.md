---
title: Iletişim kutusu uygulama
ms.date: 11/04/2016
helpviewer_keywords:
- CSimpleDialog class, implementing dialog boxes in ATL
- dialog boxes, ATL
- CAxDialogImpl class, implementing dialog boxes in ATL
- ATL, dialog boxes
ms.assetid: 478525f2-aa6a-435a-b162-68fc8aa98a8e
ms.openlocfilehash: fa7b4122b513d48194dedeb39daecd1dfd7223eb
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91499583"
---
# <a name="implementing-a-dialog-box"></a>Iletişim kutusu uygulama

ATL projenize bir iletişim kutusu eklemenin iki yolu vardır: ATL Iletişim Sihirbazı 'Nı kullanın veya el ile ekleyin.

## <a name="adding-a-dialog-box-with-the-atl-dialog-wizard"></a>ATL Iletişim kutusu Sihirbazı ile Iletişim kutusu ekleme

[Sınıf Ekle iletişim kutusunda](../ide/adding-a-class-visual-cpp.md#add-class-dialog-box), ATL projenize bir iletişim kutusu eklemek Için atl iletişim kutusu nesnesini seçin. ATL Iletişim kutusu Sihirbazı ' nı uygun olarak doldurup **son**' a tıklayın. Sihirbaz, [Caxdialogimpl](../atl/reference/caxdialogimpl-class.md) 'den türetilmiş bir sınıfı projeye ekler. **Görünüm** menüsünden **kaynak görünümü** açın, iletişim kutusunu bulun ve kaynak düzenleyicisinde açmak için çift tıklayın.

> [!NOTE]
> İletişim kutusu, ' den türetilmişse `CAxDialogImpl` , hem ActiveX hem de Windows denetimlerini barındırabilirler. İletişim kutusu sınıfınıza ActiveX denetimi desteğinin ek yükünü istemiyorsanız, bunun yerine [CSimpleDialog](../atl/reference/csimpledialog-class.md) veya [Cdialogimpl](../atl/reference/cdialogimpl-class.md) kullanın.

İleti ve olay işleyicileri, Sınıf Görünümü iletişim kutusu sınıfınıza eklenebilir. Daha fazla bilgi için bkz. [ATL Ileti Işleyicisi ekleme](../atl/adding-an-atl-message-handler.md).

## <a name="adding-a-dialog-box-manually"></a>Iletişim kutusunu el Ile ekleme

Bir iletişim kutusu uygulamak, bir pencere uygulamaya benzer. [Caxdialogimpl](../atl/reference/caxdialogimpl-class.md), [Cdialogimpl](../atl/reference/cdialogimpl-class.md)ya da [CSimpleDialog](../atl/reference/csimpledialog-class.md) 'dan bir sınıf türetirsiniz ve iletileri işlemek için bir [ileti haritası](../atl/message-maps-atl.md) bildirirsiniz. Ancak, türetilmiş sınıfınıza bir iletişim kutusu şablonu kaynak KIMLIĞI de belirtmeniz gerekir. Sınıfınız bu değeri tutmak için çağrılan bir veri üyesine sahip olmalıdır `IDD` .

> [!NOTE]
> ATL Iletişim kutusu Sihirbazı 'nı kullanarak bir iletişim kutusu oluşturduğunuzda, sihirbaz üyeyi otomatik olarak `IDD` bir tür olarak ekler **`enum`** .

`CDialogImpl` Windows denetimlerini barındıran kalıcı veya kalıcı olmayan bir iletişim kutusu uygulamanıza olanak tanır. `CAxDialogImpl` hem ActiveX hem de Windows denetimlerini barındıran kalıcı veya kalıcı olmayan bir iletişim kutusu uygulamanıza olanak tanır.

Kalıcı bir iletişim kutusu oluşturmak için, `CDialogImpl` türetilmiş (veya `CAxDialogImpl` -türetilmiş) sınıfınızın bir örneğini oluşturun ve ardından [DoModal](../atl/reference/cdialogimpl-class.md#domodal) yöntemini çağırın. Kalıcı iletişim kutusunu kapatmak için, bir ileti işleyicisinden [EndDialog](../atl/reference/cdialogimpl-class.md#enddialog) yöntemini çağırın. Kalıcı olmayan bir iletişim kutusu oluşturmak için yerine [Create](../atl/reference/cdialogimpl-class.md#create) yöntemini çağırın `DoModal` . Kalıcı olmayan bir iletişim kutusunu yok etmek için [Destroyıwindow](../atl/reference/cdialogimpl-class.md#destroywindow)' ı çağırın.

[Caxdialogimpl](../atl/reference/caxdialogimpl-class.md)'da otomatik olarak olaylar yapılır. Türetilmiş bir sınıftaki işleyicilerle yaptığınız gibi iletişim kutusunun ileti işleyicilerini uygulayın `CWindowImpl` . İletiye özgü bir dönüş değeri varsa, bunu olarak döndürün `LRESULT` . Döndürülen `LRESULT` değerler, Windows iletişim Yöneticisi tarafından uygun işleme IÇIN ATL tarafından eşleştirilir. Ayrıntılar için bkz. Cnlwin. h içinde [Cdialogimplbaset::D ıalogproc](../atl/reference/cdialogimpl-class.md#dialogproc) için kaynak kodu.

## <a name="example"></a>Örnek

Aşağıdaki sınıf bir iletişim kutusu uygular:

[!code-cpp[NVC_ATL_Windowing#66](../atl/codesnippet/cpp/implementing-a-dialog-box_1.h)]

## <a name="see-also"></a>Ayrıca bkz.

[Pencere sınıfları](../atl/atl-window-classes.md)
