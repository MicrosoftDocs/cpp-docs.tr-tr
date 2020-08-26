---
title: Tür Kitaplığı Erişimi
ms.date: 11/04/2016
helpviewer_keywords:
- type libraries [MFC], accessing
ms.assetid: a03fa7f0-86c2-4119-bf81-202916fb74b3
ms.openlocfilehash: 55d6a56f566416bb25f3ee3ae508c86f17f0df99
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88840460"
---
# <a name="type-library-access"></a>Tür Kitaplığı Erişimi

Tür kitaplıkları OLE denetiminin arabirimlerini diğer OLE uyumlu uygulamalara sunar. Bir veya daha fazla arabirim gösterilmelidir, her OLE denetiminin bir tür kitaplığı olmalıdır.

Aşağıdaki makrolar bir OLE denetiminin kendi tür kitaplığına erişim sağlamasına izin verir:

### <a name="type-library-access"></a>Tür Kitaplığı Erişimi

|Ad|Açıklama|
|-|-|
|[DECLARE_OLETYPELIB](#declare_oletypelib)|`GetTypeLib`OLE denetiminin (sınıf bildiriminde kullanılması gerekir) bir üye işlevi bildirir.|
|[IMPLEMENT_OLETYPELIB](#implement_oletypelib)|`GetTypeLib`OLE denetiminin (sınıf uygulamasında kullanılması gerekir) bir üye işlevi uygular.|

## <a name="declare_oletypelib"></a><a name="declare_oletypelib"></a> DECLARE_OLETYPELIB

`GetTypeLib`Denetim sınıfınızın üye işlevini bildirir.

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

## <a name="implement_oletypelib"></a><a name="implement_oletypelib"></a> IMPLEMENT_OLETYPELIB

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
