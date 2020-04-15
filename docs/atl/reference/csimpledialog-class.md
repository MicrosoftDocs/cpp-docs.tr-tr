---
title: CSimpleDialog Sınıfı
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
ms.openlocfilehash: 345372d71ad96a74bb0ae6dd7e89bdf0724cd822
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330833"
---
# <a name="csimpledialog-class"></a>CSimpleDialog Sınıfı

Bu sınıf temel bir modal iletişim kutusu uygular.

## <a name="syntax"></a>Sözdizimi

```
template <WORD t_wDlgTemplateID, BOOL t_bCenter = TRUE>
class CSimpleDialog : public CDialogImplBase
```

#### <a name="parameters"></a>Parametreler

*t_wDlgTemplateID*

İletişim şablonu kaynağının kaynak kimliği.

*t_bCenter*<br/>
İletişim nesnesi sahibi penceresinde ortalanacaksa DOĞRU; aksi takdirde YANLIŞ.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CSimpleDialog::DoModal](#domodal)|Modal iletişim kutusu oluşturur.|

## <a name="remarks"></a>Açıklamalar

Temel işlevselliği olan bir modal iletişim kutusu uygular. `CSimpleDialog`yalnızca Windows ortak denetimleri için destek sağlar. Modal iletişim kutusu oluşturmak ve görüntülemek için, iletişim kutusu için varolan bir kaynak şablonunun adını sağlayan bu sınıfın bir örneğini oluşturun. Kullanıcı önceden tanımlanmış bir değere sahip (IDOK veya IDCANCEL gibi) herhangi bir denetimi tıklattığında iletişim kutusu nesnesi kapanır.

`CSimpleDialog`yalnızca modal iletişim kutuları oluşturmanıza olanak sağlar. `CSimpleDialog`iletileri uygun işleyicilere yönlendirmek için varsayılan ileti eşlemesini kullanan iletişim kutusu yordamını sağlar.

Bkz. Daha fazla bilgi için [Bir İletişim Kutusu Uygulama.](../../atl/implementing-a-dialog-box.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CDialogImplBase`

`CSimpleDialog`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="csimpledialogdomodal"></a><a name="domodal"></a>CSimpleDialog::DoModal

Modal iletişim kutusunu çağırır ve yapıldığında iletişim kutusu sonucunu döndürür.

```
INT_PTR DoModal(HWND hWndParent = ::GetActiveWindow());
```

### <a name="parameters"></a>Parametreler

*hWndParent*<br/>
İletişim kutusunun üst öğesine bir tutamaç. Değer sağlanmadıysa, üst öğe geçerli etkin pencereye ayarlanır.

### <a name="return-value"></a>Dönüş Değeri

İade değeri başarılı olursa, iletişim kutusunu kapatan denetimin kaynak kimliğidir.

İşlev başarısız olursa, iade değeri -1'dir. Genişletilmiş hata bilgilerini almak `GetLastError`için .

### <a name="remarks"></a>Açıklamalar

Bu yöntem, iletişim kutusu etkinken kullanıcıyla olan tüm etkileşimi işler. Bu iletişim kutusu modal kılan şeydir; diğer bir deyişle, iletişim kutusu kapatılana kadar kullanıcı diğer pencerelerle etkileşim kuramaz.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
