---
description: ': ICommandTarget arabirimi hakkında daha fazla bilgi edinin'
title: ICommandTarget arabirimi
ms.date: 11/04/2016
f1_keywords:
- ICommandTarget
- AFXWINFORMS/ICommandTarget
- AFXWINFORMS/ICommandTarget::Initialize
helpviewer_keywords:
- ICommandTarget interface [MFC]
ms.assetid: dd9927f6-3479-4e7c-8ef9-13206cf901f3
ms.openlocfilehash: 6deb11ecca94160ea19225fb955826845a4cdefa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97219583"
---
# <a name="icommandtarget-interface"></a>ICommandTarget arabirimi

Komut kaynak nesnesinden komutları almak için arabirimi olan bir kullanıcı denetimi sağlar.

## <a name="syntax"></a>Syntax

```
interface class ICommandTarget
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[ICommandTarget:: Initialize](#initialize)|Komut hedef nesnesini başlatır.|

## <a name="remarks"></a>Açıklamalar

Bir MFC görünümünde Kullanıcı denetimini barındırdığınızda, [CWinFormsView](../../mfc/reference/cwinformsview-class.md) ve MFC komutlarının (örneğin, çerçeve menü öğeleri ve araç çubuğu düğmeleri) işlemesini sağlamak IÇIN komut UI iletilerini Kullanıcı denetimine yönlendirir. Uygulayarak `ICommandTarget` , Kullanıcı denetimine [ICommandSource](../../mfc/reference/icommandsource-interface.md) nesnesine bir başvuru verirsiniz.

Nasıl kullanılacağına ilişkin bir örnek için, bkz. [nasıl yapılır: Windows Forms denetimine komut yönlendirmesi ekleme](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) `ICommandTarget` .

Windows Forms kullanma hakkında daha fazla bilgi için bkz. [MFC 'de Windows formu Kullanıcı denetimi kullanma](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwinforms. h (derlemede tanımlanan atlmfc\lib\mfcmifc80.dll)

## <a name="icommandtargetinitialize"></a><a name="initialize"></a> ICommandTarget:: Initialize

Komut hedef nesnesini başlatır.

```cpp
void Initialize(ICommandSource^ cmdSource);
```

### <a name="parameters"></a>Parametreler

*cmdSource*<br/>
Komut kaynak nesnesine yönelik bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Bir MFC görünümünde bir Kullanıcı Denetimi barındırdığınızda, CWinFormsView komutunu yönlendirir ve MFC komutlarının işlemesini sağlamak için komut UI iletilerini Kullanıcı denetimine güncelleştirir.

Bu yöntem, komut hedef nesnesini başlatır ve belirtilen komut kaynağı nesnesi cmdSource ile ilişkilendirir. Kullanıcı denetim sınıfı uygulamasında çağrılmalıdır. Başlatma sırasında, Initialize uygulamasında ICommandText ' i çağırarak komut işleyicileri komut kaynak nesnesi ile kaydetmelisiniz. Bkz. nasıl yapılır: Windows Forms denetimine komut yönlendirmesi ekleme ve bunu yapmak için başlatma kullanma örneği.

## <a name="see-also"></a>Ayrıca bkz.

[Nasıl yapılır: Windows Forms denetimine komut yönlendirmesi ekleme](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)<br/>
[ICommandSource arabirimi](../../mfc/reference/icommandsource-interface.md)
