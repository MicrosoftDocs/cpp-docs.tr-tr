---
description: 'Daha fazla bilgi edinin: CSimpleDialog sınıfı'
title: CSimpleDialog sınıfı
ms.date: 11/04/2016
f1_keywords:
- CSimpleDialog
- ATLWIN/ATL::CSimpleDialog
- ATLWIN/ATL::CSimpleDialog::DoModal
helpviewer_keywords:
- CSimpleDialog class
- CSimpleDialog class, modal dialog boxes in ATL
- dialog boxes, modal
- modal dialog boxes, ATL
ms.assetid: 2ae65cc9-4f32-4168-aecd-200b4a480fdf
ms.openlocfilehash: 50889c4387515c85cd3c6e53bf12e7c0494504ed
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140653"
---
# <a name="csimpledialog-class"></a>CSimpleDialog sınıfı

Bu sınıf, temel kalıcı iletişim kutusu uygular.

## <a name="syntax"></a>Sözdizimi

```
template <WORD t_wDlgTemplateID, BOOL t_bCenter = TRUE>
class CSimpleDialog : public CDialogImplBase
```

#### <a name="parameters"></a>Parametreler

*t_wDlgTemplateID*

İletişim kutusu şablon kaynağının kaynak KIMLIĞI.

*t_bCenter*<br/>
İletişim kutusu nesnesi, sahip penceresinde ortalandıysanız doğru; Aksi halde yanlış.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CSimpleDialog::D oModal](#domodal)|Kalıcı bir iletişim kutusu oluşturur.|

## <a name="remarks"></a>Açıklamalar

Temel işlevsellikle kalıcı iletişim kutusu uygular. `CSimpleDialog` yalnızca Windows ortak denetimleri için destek sağlar. Kalıcı bir iletişim kutusu oluşturmak ve göstermek için, bu sınıfın bir örneğini oluşturun ve iletişim kutusu için var olan bir kaynak şablonunun adını sağlar. Kullanıcı önceden tanımlanmış bir değer (IDOK veya ıDCANCEL gibi) ile herhangi bir denetime tıkladığında iletişim kutusu nesnesi kapanır.

`CSimpleDialog` yalnızca kalıcı iletişim kutuları oluşturmanıza izin verir. `CSimpleDialog` iletileri uygun işleyicilere yönlendirmek için varsayılan ileti eşlemesini kullanan iletişim kutusu yordamını sağlar.

Daha fazla bilgi için bkz. [Iletişim kutusu uygulama](../../atl/implementing-a-dialog-box.md) .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CDialogImplBase`

`CSimpleDialog`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

## <a name="csimpledialogdomodal"></a><a name="domodal"></a> CSimpleDialog::D oModal

Kalıcı bir iletişim kutusu çağırır ve tamamlandığında iletişim kutusu sonucunu döndürür.

```
INT_PTR DoModal(HWND hWndParent = ::GetActiveWindow());
```

### <a name="parameters"></a>Parametreler

*hWndParent*<br/>
İletişim kutusunun üst öğesine yönelik bir tanıtıcı. Değer sağlanmazsa, üst öğe geçerli etkin pencereye ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, dönüş değeri iletişim kutusunu kapatılan denetimin kaynak KIMLIĞIDIR.

İşlev başarısız olursa, dönüş değeri-1 ' dir. Genişletilmiş hata bilgilerini almak için çağrısı yapın `GetLastError` .

### <a name="remarks"></a>Açıklamalar

Bu yöntem, iletişim kutusu etkinken kullanıcıyla tüm etkileşimi işler. İletişim kutusu kalıcı hale gelir; diğer bir deyişle, iletişim kutusu kapatılıncaya kadar Kullanıcı diğer pencereler ile etkileşime giremezsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)
