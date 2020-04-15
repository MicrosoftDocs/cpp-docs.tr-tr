---
title: ICommandTarget Arayüzü
ms.date: 11/04/2016
f1_keywords:
- ICommandTarget
- AFXWINFORMS/ICommandTarget
- AFXWINFORMS/ICommandTarget::Initialize
helpviewer_keywords:
- ICommandTarget interface [MFC]
ms.assetid: dd9927f6-3479-4e7c-8ef9-13206cf901f3
ms.openlocfilehash: 865a8a27d96f84f536e40ec5a7bbbbdd9837dfcd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81356911"
---
# <a name="icommandtarget-interface"></a>ICommandTarget Arayüzü

Komut kaynağı nesneden komutalmak için arabirimile kullanıcı denetimi sağlar.

## <a name="syntax"></a>Sözdizimi

```
interface class ICommandTarget
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[ICommandTarget::Initialize](#initialize)|Komut hedef nesnesini başharfe ait hale.|

## <a name="remarks"></a>Açıklamalar

Bir MFC Görünümü'nde bir kullanıcı denetimi barındırdığınızda, [CWinFormsView](../../mfc/reference/cwinformsview-class.md) komutları yönlendirir ve komut ui iletilerini kullanıcı denetimine günceller ve MFC komutlarını (örneğin, çerçeve menü öğeleri ve araç çubuğu düğmeleri) işlemesine izin verir. Uygulayarak, `ICommandTarget`kullanıcı denetimi [iCommandSource](../../mfc/reference/icommandsource-interface.md) nesnesine bir başvuru verir.

[Bkz. Nasıl Yapılır: Nasıl](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) kullanılacağına `ICommandTarget`bir örnek olarak Windows Forms Denetimi'ne Komut Yönlendirme ekleme.

Windows Formlarını kullanma hakkında daha fazla bilgi [için](../../dotnet/using-a-windows-form-user-control-in-mfc.md)bkz.

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxwinforms.h (montaj atlmfc\lib\mfcmifc80.dll tanımlanır)

## <a name="icommandtargetinitialize"></a><a name="initialize"></a>ICommandTarget::Initialize

Komut hedef nesnesini başharfe ait hale.

```
void Initialize(ICommandSource^ cmdSource);
```

### <a name="parameters"></a>Parametreler

*cmdKaynak*<br/>
Komut kaynağı nesneye bir tutamaç.

### <a name="remarks"></a>Açıklamalar

Bir MFC Görünümü'nde bir kullanıcı denetimi barındırdığınızda, CWinFormsView komutları yönlendirir ve Komut UI iletilerini mfc komutlarını işlemesine izin vermek için kullanıcı denetimine günceller.

Bu yöntem komut hedef nesnesini baş harfe doğru laştırır ve belirtilen komut kaynağı nesnesi cmdSource ile ilişkilendirer. Kullanıcı denetim sınıfı uygulamasında çağrılmalıdır. Başlatma sırasında, Komut işleyicilerini ICommandSource::AddCommandHandler'ı Initialize uygulamasında arayarak komut kaynağı nesnesi ile kaydetmelisiniz. Bkz. Nasıl Yapılır: Bunu yapmak için Initialize'i nasıl kullanacağına bir örnek olarak Windows Forms Denetimi'ne Komut Yönlendirme ekleme.

## <a name="see-also"></a>Ayrıca bkz.

[Nasıl yapılır: Windows Forms Denetimi'ne Yönlendiren Komut Ekleme](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)<br/>
[ICommandSource Arayüzü](../../mfc/reference/icommandsource-interface.md)
