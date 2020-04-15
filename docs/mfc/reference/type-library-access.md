---
title: Tür Kitaplığı Erişimi
ms.date: 11/04/2016
helpviewer_keywords:
- type libraries [MFC], accessing
ms.assetid: a03fa7f0-86c2-4119-bf81-202916fb74b3
ms.openlocfilehash: 1794e16489ab48d919bbd4116588fba4b74b88d9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372883"
---
# <a name="type-library-access"></a>Tür Kitaplığı Erişimi

Tür kitaplıkları, OLE denetiminin arabirimlerini diğer OLE'ye duyarlı uygulamalara sunar. Bir veya daha fazla arabirim açığa çıkmak için her OLE denetiminin bir tür kitaplığı olmalıdır.

Aşağıdaki makrolar, bir OLE denetiminin kendi tür kitaplığına erişim sağlamasına olanak tanır:

### <a name="type-library-access"></a>Tür Kitaplığı Erişimi

|||
|-|-|
|[DECLARE_OLETYPELIB](#declare_oletypelib)|OLE `GetTypeLib` denetiminin bir üye işlevini bildirir (sınıf bildiriminde kullanılmalıdır).|
|[IMPLEMENT_OLETYPELIB](#implement_oletypelib)|OLE `GetTypeLib` denetiminin bir üye işlevini uygular (sınıf uygulamasında kullanılmalıdır).|

## <a name="declare_oletypelib"></a><a name="declare_oletypelib"></a>DECLARE_OLETYPELIB

Denetim sınıfınızın `GetTypeLib` üye işlevini bildirir.

```
DECLARE_OLETYPELIB(class_name)
```

### <a name="parameters"></a>Parametreler

*class_name*<br/>
Tür kitaplığıyla ilgili denetim sınıfının adı.

### <a name="remarks"></a>Açıklamalar

Bu makroyu denetim sınıfı üstbilgi dosyasında kullanın.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdisp.h

## <a name="implement_oletypelib"></a><a name="implement_oletypelib"></a>IMPLEMENT_OLETYPELIB

Denetimin `GetTypeLib` üye işlevini uygular.

```
IMPLEMENT_OLETYPELIB(class_name, tlid, wVerMajor,  wVerMinor)
```

### <a name="parameters"></a>Parametreler

*class_name*<br/>
Tür kitaplığıyla ilgili denetim sınıfının adı.

*tlid*<br/>
Tür kitaplığın kimlik numarası.

*wVerMajor*<br/>
Tür kitaplığı ana sürüm numarası.

*wVerMinor*<br/>
Tür kitaplığı küçük sürüm numarası.

### <a name="remarks"></a>Açıklamalar

Bu makro, DECLARE_OLETYPELIB makrokullanan herhangi bir denetim sınıfı için uygulama dosyasında görünmelidir.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdisp.h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve Küreseller](../../mfc/reference/mfc-macros-and-globals.md)
