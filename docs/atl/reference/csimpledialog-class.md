---
title: "CSimpleDialog sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSimpleDialog
- ATLWIN/ATL::CSimpleDialog
- ATLWIN/ATL::CSimpleDialog::DoModal
dev_langs: C++
helpviewer_keywords:
- CSimpleDialog class
- CSimpleDialog class, modal dialog boxes in ATL
- dialog boxes, modal
- modal dialog boxes, ATL
ms.assetid: 2ae65cc9-4f32-4168-aecd-200b4a480fdf
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0196d5e0e1516b47936837e1282471161a191365
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="csimpledialog-class"></a>CSimpleDialog sınıfı
Bu sınıf temel kalıcı bir iletişim kutusu uygular.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <WORD t_wDlgTemplateID, BOOL t_bCenter = TRUE>  
class CSimpleDialog : public CDialogImplBase
```  
  
#### <a name="parameters"></a>Parametreler  
 *t_wDlgTemplateID*  
  
 İletişim kutusu şablon kaynağı kaynak kimliği.  
  
 *t_bCenter*  
 **DOĞRU** iletişim nesne sahibi penceresinde ortalanmış; tersi durumda ise **FALSE**.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSimpleDialog::DoModal](#domodal)|Modal bir iletişim kutusu oluşturur.|  
  
## <a name="remarks"></a>Açıklamalar  
 Modal bir iletişim kutusu ile temel işlevlerini uygular. `CSimpleDialog`Windows ortak denetimleri için yalnızca desteği sağlar. Oluşturun ve kalıcı bir iletişim kutusu görüntülemek için var olan bir kaynak şablonu adı için iletişim kutusu sağlama bu sınıfının bir örneğini oluşturun. Kullanıcı (örneğin, IDOK veya IDCANCEL) önceden tanımlanmış bir değerle herhangi bir denetimi tıklattığında iletişim kutusu nesnesini kapatır.  
  
 `CSimpleDialog`kalıcı iletişim kutuları oluşturmanıza olanak sağlar. `CSimpleDialog`Varsayılan ileti eşlemesi uygun işleyicileri iletilerini yönlendirmek için kullandığı iletişim kutusu yordam sağlar.  
  
 Bkz: [bir iletişim kutusu uygulama](../../atl/implementing-a-dialog-box.md) daha fazla bilgi için.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CDialogImplBase`  
  
 `CSimpleDialog`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h  
  
##  <a name="domodal"></a>CSimpleDialog::DoModal  
 Kalıcı iletişim kutusunu çağırır ve tamamlandığında iletişim kutusu sonucu döndürür.  
  
```
INT_PTR DoModal(HWND hWndParent = ::GetActiveWindow());
```  
  
### <a name="parameters"></a>Parametreler  
 `hWndParent`  
 İletişim kutusunun üst için bir tanıtıcı. Herhangi bir değer sağlanmazsa, üst geçerli etkin pencereyi ayarlanır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, dönüş değeri iletişim kutusu kapatılır denetimi kaynak kimliğidir.  
  
 İşlev başarısız olursa, dönüş değeri -1'dir. Genişletilmiş hata bilgilerini için arama `GetLastError`.  
  
### <a name="remarks"></a>Açıklamalar  
 İletişim kutusu etkinken bu yöntem tüm kullanıcıyla etkileşime işler. İletişim kutusu kalıcı kılan budur; diğer bir deyişle, kullanıcı iletişim kutusu kapatılana kadar diğer windows ile etkileşime giremezler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
