---
title: OLE Başlatma
ms.date: 11/04/2016
f1_keywords:
- afxdisp/AfxOleInit
- afxdisp/AfxEnableControlContainer
helpviewer_keywords:
- OLE initialization
ms.assetid: aa8a54a7-24c3-4344-b2c6-dbcf6084fa31
ms.openlocfilehash: 3d49b37ffc2561fa9a51463a893ec2ba4f4fb725
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62310287"
---
# <a name="ole-initialization"></a>OLE Başlatma

Uygulamanın OLE sistem hizmetlerini kullanmadan önce OLE sistem DLL'lerini Başlat ve DLL'leri doğru sürüm olduğundan emin olun. `AfxOleInit` İşlevi OLE sistem DLL'lerini başlatır.

### <a name="ole-initialization"></a>OLE Başlatma

|||
|-|-|
|[Afxoleınit](#afxoleinit)|OLE kitaplıklarının başlatır.|
|[AfxEnableControlContainer](#afxenablecontrolcontainer)|Uygulama nesnenizin içinde bu işlevi çağırın `InitInstance` kapsama OLE denetimlerinin desteğini etkinleştirmek için işlevi.|

## <a name="afxenablecontrolcontainer"></a> AfxEnableControlContainer

Uygulama nesnenizin içinde bu işlevi çağırın `InitInstance` kapsama OLE denetimlerinin desteğini etkinleştirmek için işlevi.

### <a name="syntax"></a>Sözdizimi

```
void AfxEnableControlContainer( );
```

### <a name="remarks"></a>Açıklamalar

OLE denetimleri (artık ActiveX denetimleri olarak da bilinir) hakkında daha fazla bilgi için bkz: [ActiveX denetimi konuları](../mfc-activex-controls.md).

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdisp.h

##  <a name="afxoleinit"></a>  Afxoleınit

OLE desteği için uygulamayı başlatır.

```
BOOL AFXAPI AfxOleInit();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; 0 OLE sistem DLL'leri yanlış sürümlerinin yüklü olduğunu başlatma, büyük olasılıkla başarısız olur.

### <a name="remarks"></a>Açıklamalar

Bir MFC uygulaması OLE desteği başlatmak için bu işlevi çağırın. Bu işlev çağrıldığında aşağıdaki eylemler gerçekleşir:

- Çağıran uygulamanın geçerli Grup COM kitaplık başlatır. Daha fazla bilgi için [OleInitialize](/windows/desktop/api/ole2/nf-ole2-oleinitialize).

- Bir ileti filtresi oluşturur, uygulama [ı](/windows/desktop/api/objidl/nn-objidl-imessagefilter) arabirimi. Bu ileti filtresi çağrısı ile erişilebilir [AfxOleGetMessageFilter](application-control.md#afxolegetmessagefilter).

> [!NOTE]
>  Varsa **Afxoleınit** çağrılır bir MFC DLL dosyasından çağrı başarısız olur. Bir DLL dosyasından çağrılırsa, OLE sistem daha önce çağıran uygulama tarafından başlatıldı, işlev varsayar hata oluşur.

> [!NOTE]
>  MFC uygulamaları tek iş parçacıklı grup (STA) başlatılması gerekir. Eğer [CoInitializeEx](/windows/desktop/api/combaseapi/nf-combaseapi-coinitializeex) içinde `InitInstance` geçersiz kılmak, COINIT_APARTMENTTHREADED (COINIT_MULTITHREADED yerine) belirtin.

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdisp.h

## <a name="see-also"></a>Ayrıca bkz.

[Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)
