---
title: OLE Başlatma
ms.date: 11/04/2016
f1_keywords:
- afxdisp/AfxOleInit
- afxdisp/AfxEnableControlContainer
helpviewer_keywords:
- OLE initialization
ms.assetid: aa8a54a7-24c3-4344-b2c6-dbcf6084fa31
ms.openlocfilehash: fefb7eda242ffe15e85cd9f0e16e947a067044a0
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751217"
---
# <a name="ole-initialization"></a>OLE Başlatma

Bir uygulama nın OLE sistem hizmetlerini kullanabilmesi için önce, OLE sistem DLL'lerini başlatması ve DL'lerin doğru sürüm olduğunu doğrulaması gerekir. İşlev `AfxOleInit` OLE sistemi DLs'i initialleştirir.

### <a name="ole-initialization"></a>OLE Başlatma

|||
|-|-|
|[AfxOleInit](#afxoleinit)|OLE kitaplıklarını başharfe alır.|
|[AfxEnableControlContainer](#afxenablecontrolcontainer)|OLE denetimlerinin kontrol edilmesi `InitInstance` için destek sağlamak için uygulama nesnenizin işlevinde bu işlevi çağırın.|

## <a name="afxenablecontrolcontainer"></a><a name="afxenablecontrolcontainer"></a>AfxEnableControlContainer

OLE denetimlerinin kontrol edilmesi `InitInstance` için destek sağlamak için uygulama nesnenizin işlevinde bu işlevi çağırın.

### <a name="syntax"></a>Sözdizimi

```cpp
void AfxEnableControlContainer( );
```

### <a name="remarks"></a>Açıklamalar

OLE denetimleri hakkında daha fazla bilgi için (şimdi ActiveX denetimleri olarak adlandırılır), [ActiveX Denetim Konuları'na](../mfc-activex-controls.md)bakın.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdisp.h

## <a name="afxoleinit"></a><a name="afxoleinit"></a>AfxOleInit

Uygulama için OLE desteğini başlatir.

```
BOOL AFXAPI AfxOleInit();
```

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; 0 başlatma başarısız olursa, büyük olasılıkla çünkü OLE sistemi DLLs yanlış sürümleri yüklenir.

### <a name="remarks"></a>Açıklamalar

Bir MFC uygulaması için OLE desteğini başlatmak için bu işlevi arayın. Bu işlev çağrıldığında, aşağıdaki eylemler oluşur:

- Arama uygulamasının geçerli dairesindecom kitaplığını başlatir. Daha fazla bilgi için Bkz. [OleInitialize](/windows/win32/api/ole2/nf-ole2-oleinitialize).

- [IMessageFilter](/windows/win32/api/objidl/nn-objidl-imessagefilter) arabirimini uygulayarak bir ileti filtresi nesnesi oluşturur. Bu ileti [filtresine AfxOleGetMessageFilter'e](application-control.md#afxolegetmessagefilter)yapılan bir çağrıyla erişilebilir.

> [!NOTE]
> **AfxOleInit** bir MFC DLL'den çağrılırsa, arama başarısız olur. İşlev, bir DLL'den çağrıldığı takdirde, OLE sisteminin daha önce arama uygulaması tarafından başlatifize edildiğini varsayar çünkü başarısızlık oluşur.

> [!NOTE]
> MFC uygulamaları tek dişli daire (STA) olarak başharfe getirilmelidir. Geçersiz kılmada `InitInstance` [CoInitializeEx'i](/windows/win32/api/combaseapi/nf-combaseapi-coinitializeex) ararsanız, COINIT_APARTMENTTHREADED belirtin (COINIT_MULTITHREADED yerine).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdisp.h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve Küreseller](../../mfc/reference/mfc-macros-and-globals.md)
