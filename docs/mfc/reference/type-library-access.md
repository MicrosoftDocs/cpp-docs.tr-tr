---
title: Tür Kitaplığı Erişimi
ms.date: 11/04/2016
helpviewer_keywords:
- type libraries [MFC], accessing
ms.assetid: a03fa7f0-86c2-4119-bf81-202916fb74b3
ms.openlocfilehash: 23d4675bd3638d2effd1b967f0729f9e70dac6de
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79420752"
---
# <a name="type-library-access"></a>Tür Kitaplığı Erişimi

Tür kitaplıkları OLE denetiminin arabirimlerini diğer OLE uyumlu uygulamalara sunar. Bir veya daha fazla arabirim gösterilmelidir, her OLE denetiminin bir tür kitaplığı olmalıdır.

Aşağıdaki makrolar bir OLE denetiminin kendi tür kitaplığına erişim sağlamasına izin verir:

### <a name="type-library-access"></a>Tür Kitaplığı Erişimi

|||
|-|-|
|[DECLARE_OLETYPELIB](#declare_oletypelib)|OLE denetiminin `GetTypeLib` üye işlevini bildirir (sınıf bildiriminde kullanılması gerekir).|
|[IMPLEMENT_OLETYPELIB](#implement_oletypelib)|OLE denetiminin `GetTypeLib` üye işlevini uygular (sınıf uygulamasında kullanılması gerekir).|

##  <a name="declare_oletypelib"></a>DECLARE_OLETYPELIB

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

**Üstbilgi:** AfxDisp. h

##  <a name="implement_oletypelib"></a>IMPLEMENT_OLETYPELIB

Denetimin `GetTypeLib` üye işlevini uygular.

```
IMPLEMENT_OLETYPELIB(class_name, tlid, wVerMajor,  wVerMinor)
```

### <a name="parameters"></a>Parametreler

*class_name*<br/>
Tür kitaplığıyla ilgili denetim sınıfının adı.

*tlıd*<br/>
Tür kitaplığının KIMLIK numarası.

*Wverana*<br/>
Tür kitaplığının ana sürüm numarası.

*wVerMinor*<br/>
Tür kitaplığının ikincil sürüm numarası.

### <a name="remarks"></a>Açıklamalar

Bu makronun, DECLARE_OLETYPELIB makrosunu kullanan herhangi bir denetim sınıfı için uygulama dosyasında görünmesi gerekir.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AfxDisp. h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve genel öğeler](../../mfc/reference/mfc-macros-and-globals.md)
