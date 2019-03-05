---
title: ICommandTarget arabirimi
ms.date: 11/04/2016
f1_keywords:
- ICommandTarget
- AFXWINFORMS/ICommandTarget
- AFXWINFORMS/ICommandTarget::Initialize
helpviewer_keywords:
- ICommandTarget interface [MFC]
ms.assetid: dd9927f6-3479-4e7c-8ef9-13206cf901f3
ms.openlocfilehash: a224b868ea1923bb4f84b0d682c71fadb63da572
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57299948"
---
# <a name="icommandtarget-interface"></a>ICommandTarget arabirimi

Bir kullanıcı denetimi komutları komut kaynak nesneden almak için bir arabirim sağlar.

## <a name="syntax"></a>Sözdizimi

```
interface class ICommandTarget
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[ICommandTarget::Initialize'ı](#initialize)|Komut hedef nesnesi başlatır.|

## <a name="remarks"></a>Açıklamalar

MFC görünümü, bir kullanıcı denetiminde barındırdığınızda [CWinFormsView](../../mfc/reference/cwinformsview-class.md) yollar komutları ve güncelleştirme komut UI iletilerini MFC komutlarını (örneğin, çerçeve menüsü ögeleri ve araç çubuğu düğmeleri) işlemelerine izin vermek için kullanıcı denetimi için. Uygulayarak `ICommandTarget`, kullanıcı denetimine bir başvuru size [ICommandSource](../../mfc/reference/icommandsource-interface.md) nesne.

Bkz: [nasıl yapılır: Komut yönlendirme Windows Forms denetimine ekleme](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) nasıl kullanılacağına ilişkin bir örnek `ICommandTarget`.

Windows Forms kullanma hakkında daha fazla bilgi için bkz. [MFC içinde Windows formu kullanıcı denetimi kullanma](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxwinforms.h (derleme atlmfc\lib\mfcmifc80.dll içinde tanımlanmıştır)

##  <a name="initialize"></a> ICommandTarget::Initialize'ı

Komut hedef nesnesi başlatır.

```
void Initialize(ICommandSource^ cmdSource);
```

### <a name="parameters"></a>Parametreler

*cmdSource*<br/>
Komut kaynak nesnesine yönelik bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

MFC görünümü olarak bir kullanıcı denetimini barındırdığınızda CWinFormsView komutları ve komut UI iletilerini MFC komutlarını işlemelerine izin vermek için kullanıcı denetimine yönlendirir.

Bu yöntem, komut hedef nesnesini başlatır ve belirtilen komut kaynak nesnesi cmdSource ile ilişkilendirir. Kullanıcı denetimi sınıf uygulamasında çağrılmalıdır. Başlatma sırasında başlatma uygulamasında arama ICommandSource::AddCommandHandler tarafından komut kaynak nesnesi ile komut işleyicileri kaydolmalıdır. Bkz: nasıl yapılır: Komut yönlendirme başlatma Bunu yapmak için nasıl kullanılacağını gösteren bir örnek Windows Forms denetimi ekleyin.

## <a name="see-also"></a>Ayrıca bkz.

[Nasıl yapılır: Windows Forms Denetimine Yönlendiren Komut Ekleme](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)<br/>
[ICommandSource Arabirimi](../../mfc/reference/icommandsource-interface.md)
