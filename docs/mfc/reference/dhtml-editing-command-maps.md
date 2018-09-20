---
title: DHTML düzenleme komutu eşlemeleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
ms.assetid: c1b49876-039e-4a26-bb24-ea98ccf254a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e31490f62c170230c41a2a2a26fcbe116d39d415
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46425073"
---
# <a name="dhtml-editing-command-maps"></a>DHTML Düzenleme Komutu Eşlemeleri

DHTML düzenleme komutlarında eşlemek için aşağıdaki makroları kullanılabilir [CHtmlEditView](../../mfc/reference/chtmleditview-class.md)-türetilmiş sınıflar. Kullanımları örneği için bkz: [HTMLEdit örnek](../../visual-cpp-samples.md).

### <a name="dhtml-editing-command-map-macros"></a>DHTML düzenleme komutu eşleme makroları

|||
|-|-|
|[DECLARE_DHTMLEDITING_CMDMAP](#declare_dhtmlediting_cmdmap)|DHTML düzenleme komutu harita üzerindeki bir sınıfı bildirir.|
|[BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap)|DHTML düzenleme komutu harita içinde bir sınıf tanımı başlatır.|
|[END_DHTMLEDITING_CMDMAP](#end_dhtmlediting_cmdmap)|DHTML düzenleme komutu harita sonunu işaretler.|
|[DHTMLEDITING_CMD_ENTRY](#dhtmlediting_cmd_entry)|Komut kimliği için bir HTML düzenleme komutu eşlemeleri.|
|[DHTMLEDITING_CMD_ENTRY_FUNC](#dhtmlediting_cmd_entry_func)|Komut kimliği, bir HTML düzenleme komut ve ileti işleyicisi eşler.|
|[DHTMLEDITING_CMD_ENTRY_TYPE](#dhtmlediting_cmd_entry_type)|Komut kimliği, bir HTML düzenleme komut ve kullanıcı arabirimi öğesi eşler.|
|[DHTMLEDITING_CMD_ENTRY_FUNC_TYPE](#dhtmlediting_cmd_entry_func_type)|HTML kullanıcı arabirimi öğesi komut ve ileti işleyicisini düzenleme için bir komut kimliği eşler.|

##  <a name="declare_dhtmlediting_cmdmap"></a>  DECLARE_DHTMLEDITING_CMDMAP

DHTML düzenleme komutu harita üzerindeki bir sınıfı bildirir.

```
DECLARE_DHTMLEDITING_CMDMAP(className)
```

### <a name="parameters"></a>Parametreler

*className*<br/>
Sınıf adı.

### <a name="remarks"></a>Açıklamalar

Bu Makro tanımında kullanılacak olan [CHtmlEditView](../../mfc/reference/chtmleditview-class.md)-türetilmiş sınıflar.

Kullanım [begın_dhtmledıtıng_cmdmap](#begin_dhtmlediting_cmdmap) haritayı uygulamak için.

### <a name="example"></a>Örnek

Bkz: [HTMLEdit örnek](../../visual-cpp-samples.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxhtml.h

##  <a name="begin_dhtmlediting_cmdmap"></a>  BEGIN_DHTMLEDITING_CMDMAP

DHTML düzenleme komutu harita içinde bir sınıf tanımı başlatır.

```
BEGIN_DHTMLEDITING_CMDMAP(className)
```

### <a name="parameters"></a>Parametreler

*className*<br/>
DHTML düzenleme komutu harita içeren sınıfın adı. Bu sınıf doğrudan veya dolaylı olarak türetilmesi [CHtmlEditView](../../mfc/reference/chtmleditview-class.md) ve [declare_dhtmledıtıng_cmdmap](#declare_dhtmlediting_cmdmap) sınıf tanımı içinde makrosu.

### <a name="remarks"></a>Açıklamalar

DHTML düzenleme komutu harita HTML düzenleme komutları için kullanıcı arabirimi komutları eşlemek için kendi sınıfınızı ekleyin.

Ardından sınıf uygulama (.cpp) dosyası begın_dhtmledıtıng_cmdmap makrosu koyun [dhtmledıtıng_cmd_entry](#dhtmlediting_cmd_entry) komutlar sınıfıdır (örneğin, gelen ıd_edıt_cut IDM_CUT için) eşlemek için makroları. Kullanım [end_dhtmledıtıng_cmdmap](#end_dhtmlediting_cmdmap) olay eşlemesi sonunu işaretlemek için makrosu.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxhtml.h

##  <a name="end_dhtmlediting_cmdmap"></a>  END_DHTMLEDITING_CMDMAP

DHTML düzenleme komutu harita sonunu işaretler.

```
END_DHTMLEDITING_CMDMAP()
```

### <a name="remarks"></a>Açıklamalar

İle kullanılmak üzere [begın_dhtmledıtıng_cmdmap](#begin_dhtmlediting_cmdmap).

### <a name="example"></a>Örnek

Bkz: [HTMLEdit örnek](../../visual-cpp-samples.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxhtml.h

##  <a name="dhtmlediting_cmd_entry"></a>  DHTMLEDITING_CMD_ENTRY

Komut kimliği için bir HTML düzenleme komutu eşlemeleri.

```
DHTMLEDITING_CMD_ENTRY(cmdID,  dhtmlcmdID)
```

### <a name="parameters"></a>Parametreler

*cmdID*<br/>
Komut Kimliği (örneğin, ıd_edıt_copy).

*dhtmlcmdID*<br/>
Hangi komut düzenleme HTML *cmdID* (IDM_COPY gibi) eşleştirir.

### <a name="example"></a>Örnek

Bkz: [HTMLEdit örnek](../../visual-cpp-samples.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxhtml.h

##  <a name="dhtmlediting_cmd_entry_func"></a>  DHTMLEDITING_CMD_ENTRY_FUNC

Komut kimliği, bir HTML düzenleme komut ve ileti işleyicisi eşler.

```
DHTMLEDITING_CMD_ENTRY_FUNC(cmdID, dhtmlcmdID,  member_func_name)
```

### <a name="parameters"></a>Parametreler

*cmdID*<br/>
Komut Kimliği (örneğin, ıd_edıt_copy).

*dhtmlcmdID*<br/>
Hangi komut düzenleme HTML *cmdID* (IDM_COPY gibi) eşleştirir.

*member_func_name*<br/>
Komut için eşlenmiş ileti işleyici işlevinin adı.

### <a name="example"></a>Örnek

Bkz: [HTMLEdit örnek](../../visual-cpp-samples.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxhtml.h

##  <a name="dhtmlediting_cmd_entry_type"></a>  DHTMLEDITING_CMD_ENTRY_TYPE

Komut kimliği, bir HTML düzenleme komut ve kullanıcı arabirimi öğesi eşler.

```
DHTMLEDITING_CMD_ENTRY_TYPE(cmdID  ,   dhtmlcmdID  ,    elemType)
```

### <a name="parameters"></a>Parametreler

*cmdID*<br/>
Komut Kimliği (örneğin, ıd_edıt_copy).

*dhtmlcmdID*<br/>
Hangi komut düzenleme HTML *cmdID* (IDM_COPY gibi) eşleştirir.

*elemType*<br/>
Kullanıcı arabirimi öğesi türü; AFX_UI_ELEMTYPE_NORMAL, AFX_UI_ELEMTYPE_CHECKBOX veya AFX_UI_ELEMTYPE_RADIO biri.

### <a name="example"></a>Örnek

Bkz: [HTMLEdit örnek](../../visual-cpp-samples.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxhtml.h

##  <a name="dhtmlediting_cmd_entry_func_type"></a>  DHTMLEDITING_CMD_ENTRY_FUNC_TYPE

HTML kullanıcı arabirimi öğesi komut ve ileti işleyicisini düzenleme için bir komut kimliği eşler.

```
DHTMLEDITING_CMD_ENTRY_FUNC_TYPE(cmdID, dhtmlcmdID, member_func_name,  elemType)
```

### <a name="parameters"></a>Parametreler

*cmdID*<br/>
Komut Kimliği (örneğin, ıd_edıt_copy).

*dhtmlcmdID*<br/>
Hangi komut düzenleme HTML *cmdID* (IDM_COPY gibi) eşleştirir.

*member_func_name*<br/>
Komut için eşlenmiş ileti işleyici işlevinin adı.

*elemType*<br/>
Kullanıcı arabirimi öğesi türü; AFX_UI_ELEMTYPE_NORMAL, AFX_UI_ELEMTYPE_CHECKBOX veya AFX_UI_ELEMTYPE_RADIO biri.

### <a name="example"></a>Örnek

Bkz: [HTMLEdit örnek](../../visual-cpp-samples.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxhtml.h

## <a name="see-also"></a>Ayrıca Bkz.

[Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)
