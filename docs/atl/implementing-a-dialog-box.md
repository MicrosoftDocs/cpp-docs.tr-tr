---
title: "Bir iletişim kutusu uygulama | Microsoft Docs"
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
- CSimpleDialog class, implementing dialog boxes in ATL
- dialog boxes, ATL
- CAxDialogImpl class, implementing dialog boxes in ATL
- ATL, dialog boxes
ms.assetid: 478525f2-aa6a-435a-b162-68fc8aa98a8e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9b3ff0e58623a241160da21266d085753be1c457
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="implementing-a-dialog-box"></a>Bir iletişim kutusu uygulama
Bir iletişim kutusu ATL projenize eklemek için iki yolu vardır: ATL iletişim Sihirbazı'nı kullanın veya el ile ekleyin.  
  
## <a name="adding-a-dialog-box-with-the-atl-dialog-wizard"></a>ATL iletişim Sihirbazı'nı içeren bir iletişim kutusu ekleme  
 İçinde [Sınıf Ekle iletişim kutusu](../ide/add-class-dialog-box.md), bir iletişim kutusu ATL projenize eklemek için ATL iletişim nesne seçin. ' I tıklatın ve uygun şekilde ATL iletişim Sihirbazı'nı doldurmanız **son**. Sihirbaz türetilmiş bir sınıf ekler [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md) projenize. Kaynak görünümünden **Görünüm** menüsünde iletişim bulun ve kaynak düzenleyicisinde açmak için çift tıklatın.  
  
> [!NOTE]
>  İletişim kutusu türetilir varsa `CAxDialogImpl`, her iki ActiveX barındırabilir ve Windows denetler. İletişim kutusu sınıfınızda ActiveX denetimi desteği yükü istemiyorsanız kullanın [CSimpleDialog](../atl/reference/csimpledialog-class.md) veya [Cdialogımpl](../atl/reference/cdialogimpl-class.md) yerine.  
  
 İletisi ve olay işleyicileri sınıfını görünümünden iletişim sınıfınızı eklenebilir. Daha fazla bilgi için bkz: [ATL ileti işleyicisi ekleme](../atl/adding-an-atl-message-handler.md).  
  
## <a name="adding-a-dialog-box-manually"></a>Bir iletişim kutusu el ile ekleme  
 Bir iletişim kutusu uygulama, bir pencere uygulamak için benzer. Herhangi birinden bir sınıf türetin [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md), [Cdialogımpl](../atl/reference/cdialogimpl-class.md), veya [CSimpleDialog](../atl/reference/csimpledialog-class.md) ve bildirme bir [ileti eşlemesi](../atl/message-maps-atl.md) iletileri işlemek için. Ancak, türetilen sınıfta de bir iletişim şablonunu kaynak kimliği belirtmeniz gerekir. Sınıfınızda adlı bir veri üyesi olmalıdır `IDD` bu değer tutmak için.  
  
> [!NOTE]
>  ATL iletişim Sihirbazı'nı kullanarak bir iletişim kutusu oluşturduğunuzda, sihirbaz otomatik olarak ekler `IDD` üye olarak bir `enum` türü.  
  
 `CDialogImpl`kalıcı bir ya da Windows denetimleri barındıran bir kalıcı olmayan iletişim kutusu uygulanmasını sağlar. `CAxDialogImpl`kalıcı bir ya da ActiveX ve Windows denetimleri barındıran bir kalıcı olmayan iletişim kutusu uygulanmasını sağlar.  
  
 Modal bir iletişim kutusu oluşturmak için bir örneğini oluşturun, `CDialogImpl`-türetilen (veya `CAxDialogImpl`-türetilen) sınıf ve ardından arama [DoModal](../atl/reference/cdialogimpl-class.md#domodal) yöntemi. Kalıcı iletişim kutusunu kapatmak için arama [EndDialog](../atl/reference/cdialogimpl-class.md#enddialog) bir ileti işleyicisini yönteminden. Kalıcı olmayan iletişim kutusu oluşturmak için çağrı [oluşturma](../atl/reference/cdialogimpl-class.md#create) yöntemi yerine `DoModal`. Kalıcı olmayan iletişim kutusunu yok etme çağrısı [DestroyWindow](../atl/reference/cdialogimpl-class.md#destroywindow).  
  
 Olayları indirme otomatik olarak yapılır [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md). İşleyiciler gibi iletişim kutusunun ileti işleyicileri uygulayan bir `CWindowImpl`-türetilmiş sınıf. İleti özgü dönüş değeri ise olarak döner bir `LRESULT`. Döndürülen `LRESULT` değerleri Windows iletişim Yöneticisi tarafından uygun işleme ATL tarafından eşlendi. Ayrıntılar için kaynak kodunu bkz [CDialogImplBaseT::DialogProc](../atl/reference/cdialogimpl-class.md#dialogproc) atlwin.h içinde.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki sınıf bir iletişim kutusu uygular:  
  
 [!code-cpp[NVC_ATL_Windowing#66](../atl/codesnippet/cpp/implementing-a-dialog-box_1.h)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pencere sınıfları](../atl/atl-window-classes.md)

