---
title: Tür Kitaplığı Erişimi
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.macros
helpviewer_keywords:
- type libraries [MFC], accessing
ms.assetid: a03fa7f0-86c2-4119-bf81-202916fb74b3
ms.openlocfilehash: d5aa92d520e2a806837ceb5208ca1262504ee02e
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57301980"
---
# <a name="type-library-access"></a>Tür Kitaplığı Erişimi

Tür kitaplıkları OLE kullanan diğer uygulamalar için bir OLE denetim arabirimleri kullanıma sunar. Bir veya daha fazla arabirim sağlamak olması durumunda her bir OLE denetimi tür kitaplığı olması gerekir.

Aşağıdaki makroları, kendi tür kitaplığı erişimi sağlamak bir OLE denetimi izin ver:

### <a name="type-library-access"></a>Tür Kitaplığı Erişimi

|||
|-|-|
|[DECLARE_OLETYPELIB](#declare_oletypelib)|Bildiren bir `GetTypeLib` (sınıf bildirimi içinde kullanılmalıdır) bir OLE denetim üye işlevi.|
|[IMPLEMENT_OLETYPELIB](#implement_oletypelib)|Uygulayan bir `GetTypeLib` (sınıfı uygulamasında kullanılmalıdır) bir OLE denetim üye işlevi.|

##  <a name="declare_oletypelib"></a>  DECLARE_OLETYPELIB

Bildirir `GetTypeLib` denetim sınıfınızın bir üye işlevi.

```
DECLARE_OLETYPELIB(class_name)
```

### <a name="parameters"></a>Parametreler

*$class_name*<br/>
Tür kitaplığına ilgili denetim sınıfı adı.

### <a name="remarks"></a>Açıklamalar

Bu makro denetim sınıf üstbilgi dosyasında kullanın.

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdisp.h

##  <a name="implement_oletypelib"></a>  IMPLEMENT_OLETYPELIB

Denetimin uygulayan `GetTypeLib` üye işlevi.

```
IMPLEMENT_OLETYPELIB(class_name, tlid, wVerMajor,  wVerMinor)
```

### <a name="parameters"></a>Parametreler

*$class_name*<br/>
Tür kitaplığına ilgili denetim sınıfı adı.

*tlid*<br/>
Tür kitaplığını kimliği sayısı.

*wVerMajor*<br/>
Tür kitaplığı ana sürüm numarası.

*wVerMinor*<br/>
Tür kitaplığı ikincil sürüm numarası.

### <a name="remarks"></a>Açıklamalar

Bu makro, declare_oletypelıb makrosu kullanan herhangi bir denetim sınıf için uygulama dosyasında yer almalıdır.

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdisp.h

## <a name="see-also"></a>Ayrıca bkz.

[Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)
