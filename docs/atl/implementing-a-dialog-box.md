---
title: İletişim kutusu uygulama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CSimpleDialog class, implementing dialog boxes in ATL
- dialog boxes, ATL
- CAxDialogImpl class, implementing dialog boxes in ATL
- ATL, dialog boxes
ms.assetid: 478525f2-aa6a-435a-b162-68fc8aa98a8e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4c5133960cca3aab3d4bf526179fd9c825c41a20
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37848463"
---
# <a name="implementing-a-dialog-box"></a>İletişim kutusu uygulama
Bir iletişim kutusu, ATL projesine eklemek için iki yolu vardır: ATL iletişim kutusu Sihirbazı'nı kullanın veya el ile ekleyin.  
  
## <a name="adding-a-dialog-box-with-the-atl-dialog-wizard"></a>ATL iletişim kutusu Sihirbazı ile bir iletişim kutusu ekleme  
 İçinde [Sınıf Ekle iletişim kutusu](../ide/add-class-dialog-box.md), bir iletişim kutusu, ATL projesine eklemek için ATL iletişim kutusu nesnesini seçin. ATL iletişim kutusu Sihirbazı uygun şekilde doldurun ve **son**. Türetilen bir sınıf sihirbaz ekler [Caxdialogımpl](../atl/reference/caxdialogimpl-class.md) projenize. Kaynak görünümünden **görünümü** menüsünde iletişim bulun ve Kaynak Düzenleyicisi'nde açmak için çift tıklayın.  
  
> [!NOTE]
>  Varsa, iletişim kutusu türetilir `CAxDialogImpl`, her iki ActiveX barındırabilir ve Windows denetler. ActiveX denetimi desteği yükü iletişim kutusu sınıfınızda istemiyorsanız kullanın [CSimpleDialog](../atl/reference/csimpledialog-class.md) veya [Cdialogımpl](../atl/reference/cdialogimpl-class.md) yerine.  
  
 İleti ve olay işleyicileri, sınıf görünümünden iletişim sınıfınızı eklenebilir. Daha fazla bilgi için [ATL ileti işleyicisi ekleme](../atl/adding-an-atl-message-handler.md).  
  
## <a name="adding-a-dialog-box-manually"></a>Bir iletişim kutusu el ile ekleme  
 İletişim kutusu uygulama pencere uygulama için benzerdir. Öğesinden bir sınıf türetin [Caxdialogımpl](../atl/reference/caxdialogimpl-class.md), [Cdialogımpl](../atl/reference/cdialogimpl-class.md), veya [CSimpleDialog](../atl/reference/csimpledialog-class.md) ve bildirmek bir [ileti eşlemesi](../atl/message-maps-atl.md) iletileri işlemek için. Ancak, türetilmiş sınıf içinde de bir iletişim şablonunu kaynak kimliği belirtmeniz gerekir. Sınıfınıza adlı bir veri üyesi olmalıdır `IDD` bu değerini tutacak.  
  
> [!NOTE]
>  ATL iletişim kutusu Sihirbazı'nı kullanarak bir iletişim kutusu oluşturduğunuzda, sihirbaz otomatik olarak ekler `IDD` üyesi olarak bir **enum** türü.  
  
 `CDialogImpl` kalıcı bir ya da Windows denetimlerini barındıran modsuz iletişim kutusu olanak tanır. `CAxDialogImpl` kalıcı bir ya da ActiveX hem Windows denetimlerini barındıran modsuz iletişim kutusu olanak tanır.  
  
 Kalıcı bir iletişim kutusu oluşturmak için bir örneğini oluşturmak, `CDialogImpl`-türetilmiş (veya `CAxDialogImpl`-türetilmiş) sınıfı ve sonra çağrı [DoModal](../atl/reference/cdialogimpl-class.md#domodal) yöntemi. Kalıcı iletişim kutusunu kapatmak için çağrı [EndDialog](../atl/reference/cdialogimpl-class.md#enddialog) yöntemden bir ileti işleyicisi. Modsuz iletişim kutusu oluşturmak için arama [Oluştur](../atl/reference/cdialogimpl-class.md#create) yöntemi yerine `DoModal`. Modsuz iletişim kutusu yok etmek için çağrı [DestroyWindow](../atl/reference/cdialogimpl-class.md#destroywindow).  
  
 İndirme olayları otomatik olarak gerçekleştirilir [Caxdialogımpl](../atl/reference/caxdialogimpl-class.md). İşleyicileri gibi iletişim kutusunun ileti işleyicilerini uygulayan bir `CWindowImpl`-türetilmiş sınıf. İletiye özgü dönüş değeri varsa, olarak iade bir `LRESULT`. Döndürülen `LRESULT` değerleri Windows iletişim Yöneticisi tarafından uygun işleme için ATL göre eşleştirilir. Ayrıntılar için kaynak kodu bkz [CDialogImplBaseT::DialogProc](../atl/reference/cdialogimpl-class.md#dialogproc) atlwin.h içinde.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki sınıf bir iletişim kutusu uygular:  
  
 [!code-cpp[NVC_ATL_Windowing#66](../atl/codesnippet/cpp/implementing-a-dialog-box_1.h)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pencere sınıfları](../atl/atl-window-classes.md)

