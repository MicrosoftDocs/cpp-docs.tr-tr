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
ms.openlocfilehash: 1d040f3cb4c9bf8e1f3afc0e8213cd4513fc8571
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37123376"
---
# <a name="dhtml-editing-command-maps"></a>DHTML Düzenleme Komutu Eşlemeleri
DHTML düzenleme komutlarda eşlemek için aşağıdaki makroları kullanılabilir [CHtmlEditView](../../mfc/reference/chtmleditview-class.md)-türetilmiş sınıfları. Kullanım örneği için bkz [HTMLEdit örnek](../../visual-cpp-samples.md).  
  
### <a name="dhtml-editing-command-map-macros"></a>DHTML düzenleme komutu eşleme makroları  
  
|||  
|-|-|  
|[DECLARE_DHTMLEDITING_CMDMAP](#declare_dhtmlediting_cmdmap)|DHTML düzenleme komutu eşlemde bir sınıftaki bildirir.|  
|[BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap)|DHTML düzenleme komutu eşlemde bir sınıftaki tanımını başlatır.|  
|[END_DHTMLEDITING_CMDMAP](#end_dhtmlediting_cmdmap)|DHTML düzenleme komutu harita sonunu işaretler.|  
|[DHTMLEDITING_CMD_ENTRY](#dhtmlediting_cmd_entry)|Komut kimliği için bir HTML düzenleme komutu eşlemeleri.|  
|[DHTMLEDITING_CMD_ENTRY_FUNC](#dhtmlediting_cmd_entry_func)|Komut kimliği, bir HTML düzenleme komut ve ileti işleyicisi eşler.|  
|[DHTMLEDITING_CMD_ENTRY_TYPE](#dhtmlediting_cmd_entry_type)|Komut kimliği, bir HTML düzenleme komut ve kullanıcı arabirimi öğesi eşler.|  
|[DHTMLEDITING_CMD_ENTRY_FUNC_TYPE](#dhtmlediting_cmd_entry_func_type)|Komut Kimliği düzenleme komutu, ileti işleyicisi ve kullanıcı arabirimi öğesi bir HTML eşler.|  
  
##  <a name="declare_dhtmlediting_cmdmap"></a>  DECLARE_DHTMLEDITING_CMDMAP  
 DHTML düzenleme komutu eşlemde bir sınıftaki bildirir.  
  
```  
DECLARE_DHTMLEDITING_CMDMAP(className)   
```  
  
### <a name="parameters"></a>Parametreler  
 *className*  
 Sınıfın adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu makrosu tanımında kullanılacaksa [CHtmlEditView](../../mfc/reference/chtmleditview-class.md)-türetilmiş sınıfları.  
  
 Kullanım [begın_dhtmledıtıng_cmdmap](#begin_dhtmlediting_cmdmap) eşleme uygulamak için.  
  
### <a name="example"></a>Örnek  
 Bkz: [HTMLEdit örnek](../../visual-cpp-samples.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxhtml.h  
  
##  <a name="begin_dhtmlediting_cmdmap"></a>  BEGIN_DHTMLEDITING_CMDMAP  
 DHTML düzenleme komutu eşlemde bir sınıftaki tanımını başlatır.  
  
```  
BEGIN_DHTMLEDITING_CMDMAP(className)   
```  
  
### <a name="parameters"></a>Parametreler  
 *className*  
 DHTML düzenleme komutu eşleme içeren sınıfın adı. Bu sınıf doğrudan veya dolaylı olarak öğesinden türetilen [CHtmlEditView](../../mfc/reference/chtmleditview-class.md) ve dahil [declare_dhtmledıtıng_cmdmap](#declare_dhtmlediting_cmdmap) makrosu sınıf tanımına içinde.  
  
### <a name="remarks"></a>Açıklamalar  
 DHTML düzenleme komutu harita HTML düzenleme komutları için kullanıcı arabirimi komutları eşleştirmek için sınıfınıza ekleyin.  
  
 Begın_dhtmledıtıng_cmdmap makrosu arkasından sınıfının uygulaması (.cpp) dosyasına koyun [dhtmledıtıng_cmd_entry](#dhtmlediting_cmd_entry) makroları sınıftır (örneğin, IDM_CUT ıd_edıt_cut) eşlenecek komutları için. Kullanım [end_dhtmledıtıng_cmdmap](#end_dhtmlediting_cmdmap) makrosu olay eşlemesi sonunu işaretler.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxhtml.h  
  
##  <a name="end_dhtmlediting_cmdmap"></a>  END_DHTMLEDITING_CMDMAP  
 DHTML düzenleme komutu harita sonunu işaretler.  
  
```  
END_DHTMLEDITING_CMDMAP()   
```  
  
### <a name="remarks"></a>Açıklamalar  
 İle birlikte [begın_dhtmledıtıng_cmdmap](#begin_dhtmlediting_cmdmap).  
  
### <a name="example"></a>Örnek  
 Bkz: [HTMLEdit örnek](../../visual-cpp-samples.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxhtml.h  
  
##  <a name="dhtmlediting_cmd_entry"></a>  DHTMLEDITING_CMD_ENTRY  
 Komut kimliği için bir HTML düzenleme komutu eşlemeleri.  
  
```  
DHTMLEDITING_CMD_ENTRY(cmdID,  dhtmlcmdID)   
```  
  
### <a name="parameters"></a>Parametreler  
 *cmdID*  
 Komut Kimliği (örneğin, ıd_edıt_copy).  
  
 *dhtmlcmdID*  
 Komutu hangi düzenleme HTML *cmdID* (IDM_COPY gibi) eşleştirir.  
  
### <a name="example"></a>Örnek  
 Bkz: [HTMLEdit örnek](../../visual-cpp-samples.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxhtml.h  
  
##  <a name="dhtmlediting_cmd_entry_func"></a>  DHTMLEDITING_CMD_ENTRY_FUNC  
 Komut kimliği, bir HTML düzenleme komut ve ileti işleyicisi eşler.  
  
```  
DHTMLEDITING_CMD_ENTRY_FUNC(cmdID, dhtmlcmdID,  member_func_name)   
```  
  
### <a name="parameters"></a>Parametreler  
 *cmdID*  
 Komut Kimliği (örneğin, ıd_edıt_copy).  
  
 *dhtmlcmdID*  
 Komutu hangi düzenleme HTML *cmdID* (IDM_COPY gibi) eşleştirir.  
  
 *member_func_name*  
 Komut eşlenmiş ileti işleyicisi işlevin adı.  
  
### <a name="example"></a>Örnek  
 Bkz: [HTMLEdit örnek](../../visual-cpp-samples.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxhtml.h  
  
##  <a name="dhtmlediting_cmd_entry_type"></a>  DHTMLEDITING_CMD_ENTRY_TYPE  
 Komut kimliği, bir HTML düzenleme komut ve kullanıcı arabirimi öğesi eşler.  
  
```  
DHTMLEDITING_CMD_ENTRY_TYPE(cmdID  ,   dhtmlcmdID  ,    elemType)  
```  
  
### <a name="parameters"></a>Parametreler  
 *cmdID*  
 Komut Kimliği (örneğin, ıd_edıt_copy).  
  
 *dhtmlcmdID*  
 Komutu hangi düzenleme HTML *cmdID* (IDM_COPY gibi) eşleştirir.  
  
 *elemType*  
 Kullanıcı arabirimi öğesi türü; AFX_UI_ELEMTYPE_NORMAL, AFX_UI_ELEMTYPE_CHECKBOX veya AFX_UI_ELEMTYPE_RADIO biri.  
  
### <a name="example"></a>Örnek  
 Bkz: [HTMLEdit örnek](../../visual-cpp-samples.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxhtml.h  
  
##  <a name="dhtmlediting_cmd_entry_func_type"></a>  DHTMLEDITING_CMD_ENTRY_FUNC_TYPE  
 Komut Kimliği düzenleme komutu, ileti işleyicisi ve kullanıcı arabirimi öğesi bir HTML eşler.  
  
```  
DHTMLEDITING_CMD_ENTRY_FUNC_TYPE(cmdID, dhtmlcmdID, member_func_name,  elemType)   
```  
  
### <a name="parameters"></a>Parametreler  
 *cmdID*  
 Komut Kimliği (örneğin, ıd_edıt_copy).  
  
 *dhtmlcmdID*  
 Komutu hangi düzenleme HTML *cmdID* (IDM_COPY gibi) eşleştirir.  
  
 *member_func_name*  
 Komut eşlenmiş ileti işleyicisi işlevin adı.  
  
 *elemType*  
 Kullanıcı arabirimi öğesi türü; AFX_UI_ELEMTYPE_NORMAL, AFX_UI_ELEMTYPE_CHECKBOX veya AFX_UI_ELEMTYPE_RADIO biri.  
  
### <a name="example"></a>Örnek  
 Bkz: [HTMLEdit örnek](../../visual-cpp-samples.md).  

### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxhtml.h  
    
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)
