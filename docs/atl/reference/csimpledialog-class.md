---
title: CSimpleDialog sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CSimpleDialog
- ATLWIN/ATL::CSimpleDialog
- ATLWIN/ATL::CSimpleDialog::DoModal
dev_langs:
- C++
helpviewer_keywords:
- CSimpleDialog class
- CSimpleDialog class, modal dialog boxes in ATL
- dialog boxes, modal
- modal dialog boxes, ATL
ms.assetid: 2ae65cc9-4f32-4168-aecd-200b4a480fdf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0a476daeb680048c7bbb21565014487f6b937c78
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43754897"
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

İletişim şablon kaynağı kaynak kimliği.

*t_bCenter*  
İletişim nesnesi üzerinde sahip pencereyi ortalamak için ise TRUE; Aksi durumda FALSE.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CSimpleDialog::DoModal](#domodal)|Kalıcı bir iletişim kutusu oluşturur.|

## <a name="remarks"></a>Açıklamalar

Kalıcı bir iletişim kutusu ile temel işlevselliğini uygular. `CSimpleDialog` Windows ortak denetimleri için yalnızca destek sağlar. Oluşturun ve kalıcı bir iletişim kutusu görüntülemek için mevcut bir kaynak şablonu adı için iletişim kutusu sağlama, bu sınıfın bir örneğini oluşturun. Kullanıcı (örneğin, IDOK veya IDCANCEL) önceden tanımlı bir değer ile herhangi bir denetimi tıklattığında iletişim kutusu nesnesini kapatır.

`CSimpleDialog` kalıcı iletişim kutuları oluşturmanıza olanak sağlar. `CSimpleDialog` uygun işleyicileri iletilerini yönlendirmek için varsayılan ileti eşlemesi kullanan iletişim kutusu yordam sağlar.

Bkz: [iletişim kutusu uygulama](../../atl/implementing-a-dialog-box.md) daha fazla bilgi için.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CDialogImplBase`

`CSimpleDialog`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlwin.h

##  <a name="domodal"></a>  CSimpleDialog::DoModal

Kalıcı bir iletişim kutusu çağırır ve işiniz bittiğinde iletişim kutusu sonucu döndürür.

```
INT_PTR DoModal(HWND hWndParent = ::GetActiveWindow());
```

### <a name="parameters"></a>Parametreler

*hWndParent*  
İletişim kutusunun üst tanıtıcı. Herhangi bir değer sağlanmazsa, geçerli etkin pencereyi üst ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, dönüş değeri iletişim kutusu kapatıldı denetimi kaynak kimliğidir.

İşlev başarısız olursa, dönüş değeri -1'dir. Genişletilmiş hata bilgilerini almak için arama `GetLastError`.

### <a name="remarks"></a>Açıklamalar

İletişim kutusu etkin olduğu sırada bu yöntem tüm etkileşime girmesinin işler. Bu iletişim kutusu kalıcı olmasını sağlayan nedir, diğer bir deyişle, kullanıcı iletişim kutusu kapatılana kadar diğer windows ile etkileşime giremezler.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfına genel bakış](../../atl/atl-class-overview.md)
