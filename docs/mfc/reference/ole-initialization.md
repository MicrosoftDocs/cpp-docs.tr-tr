---
description: 'Daha fazla bilgi edinin: OLE başlatma'
title: OLE Başlatma
ms.date: 11/04/2016
f1_keywords:
- afxdisp/AfxOleInit
- afxdisp/AfxEnableControlContainer
helpviewer_keywords:
- OLE initialization
ms.assetid: aa8a54a7-24c3-4344-b2c6-dbcf6084fa31
ms.openlocfilehash: 0efed4fefe62b720852905b6eed44501d4369efa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218998"
---
# <a name="ole-initialization"></a>OLE Başlatma

Bir uygulamanın OLE sistem hizmetlerini kullanabilmesi için, OLE sistem dll 'Lerini başlatması ve DLL 'Lerin doğru sürüm olduğunu doğrulaması gerekir. `AfxOleInit`IşLEVI OLE sistem dll 'lerini başlatır.

### <a name="ole-initialization"></a>OLE Başlatma

|Ad|Açıklama|
|-|-|
|[AfxOleInit](#afxoleinit)|OLE kitaplıklarını başlatır.|
|[AfxEnableControlContainer](#afxenablecontrolcontainer)|`InitInstance`OLE denetimlerinin kapsama desteğini etkinleştirmek için uygulama nesnenizin işlevinde bu işlevi çağırın.|

## <a name="afxenablecontrolcontainer"></a><a name="afxenablecontrolcontainer"></a> AfxEnableControlContainer

`InitInstance`OLE denetimlerinin kapsama desteğini etkinleştirmek için uygulama nesnenizin işlevinde bu işlevi çağırın.

### <a name="syntax"></a>Syntax

```cpp
void AfxEnableControlContainer( );
```

### <a name="remarks"></a>Açıklamalar

OLE denetimleri hakkında daha fazla bilgi için (artık ActiveX denetimleri olarak adlandırılır) bkz. [ActiveX denetimi konuları](../mfc-activex-controls.md).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AfxDisp. h

## <a name="afxoleinit"></a><a name="afxoleinit"></a> AfxOleInit

Uygulama için OLE desteğini başlatır.

```
BOOL AFXAPI AfxOleInit();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; 0 başlatması başarısız olursa, büyük olasılıkla OLE sistem dll 'Lerinin yanlış sürümleri yüklü.

### <a name="remarks"></a>Açıklamalar

MFC uygulaması için OLE desteğini başlatmak üzere bu işlevi çağırın. Bu işlev çağrıldığında, aşağıdaki eylemler gerçekleşir:

- Çağıran uygulamanın geçerli grubu üzerinde COM kitaplığını başlatır. Daha fazla bilgi için bkz. [OleInitialize](/windows/win32/api/ole2/nf-ole2-oleinitialize).

- [IMessageFilter](/windows/win32/api/objidl/nn-objidl-imessagefilter) arabirimini uygulayarak bir ileti filtresi nesnesi oluşturur. Bu ileti filtresi, [AfxOleGetMessageFilter](application-control.md#afxolegetmessagefilter)çağrısıyla erişilebilir.

> [!NOTE]
> Bir MFC DLL 'den **AfxOleInit** çağrılırsa, çağrı başarısız olur. Hata oluşur çünkü işlev DLL 'den çağrılırsa OLE sisteminin daha önce çağıran uygulama tarafından başlatılmış olduğunu varsaymaktadır.

> [!NOTE]
> MFC uygulamalarının tek iş parçacıklı grup (STA) olarak başlatılması gerekir. Geçersiz kılmada [CoInitializeEx](/windows/win32/api/combaseapi/nf-combaseapi-coinitializeex) öğesini çağırırsanız `InitInstance` , COINIT_APARTMENTTHREADED belirtin (COINIT_MULTITHREADED yerine).

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AfxDisp. h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve genel öğeler](../../mfc/reference/mfc-macros-and-globals.md)
