---
title: "OLE denetimleri için iletişim kutusu veri değişimi işlevleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AFXDISP/DDX_OCBool
- AFXDISP/DDX_OCBoolRO
- AFXDISP/DDX_OCColor
- AFXDISP/DDX_OCColorRO
- AFXDISP/DDX_OCFloat
- AFXDISP/DDX_OCFloatRO
- AFXDISP/DDX_OCInt
- AFXDISP/DDX_OCIntRO
- AFXDISP/DDX_OCShort
- AFXDISP/DDX_OCShortRO
- AFXDISP/DDX_OCText
- AFXDISP/DDX_OCTextRO
dev_langs:
- C++
helpviewer_keywords:
- OLE controls [MFC], DDX functions
- DDX (dialog data exchange), OLE support
ms.assetid: 7ef1f288-ff65-40d4-aad2-5497bc00bb27
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ad97690ca948525e9a0920d087e4dfd617a11b4d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="dialog-data-exchange-functions-for-ole-controls"></a>OLE Denetimleri için İletişim Kutusu Veri Değişimi İşlevleri
Bu konu, bir iletişim kutusu, form görünümü veya denetim görünüm nesnesi OLE denetimi özelliği veri üyesi iletişim kutusunda, form görünümü veya denetim görünüm nesnesi arasında veri değişimi için kullanılan DDX_OC işlevleri listeler.  
  
### <a name="ddxoc-functions"></a>DDX_OC işlevleri  
  
|||  
|-|-|  
|[DDX_OCBool](#ddx_ocbool)|Aktarımını yönetir **BOOL** OLE denetimi özelliği arasında veri ve **BOOL** veri üyesi.|  
|[DDX_OCBoolRO](#ddx_ocboolro)|Aktarımını yönetir **BOOL** OLE denetimi bir salt okunur özelliği arasında veri ve **BOOL** veri üyesi.|  
|[DDX_OCColor](#ddx_occolor)|Aktarımını yönetir **OLE_COLOR** OLE denetimi özelliği arasında veri ve bir **OLE_COLOR** veri üyesi.|  
|[DDX_OCColorRO](#ddx_occolorro)|Aktarımını yönetir **OLE_COLOR** OLE denetimi bir salt okunur özelliği arasında veri ve bir **OLE_COLOR** veri üyesi.|  
|[DDX_OCFloat](#ddx_ocfloat)|Aktarımını yönetir **float** (veya **çift**) OLE denetimi özelliği arasında veri ve **float** (veya **çift**) veri üyesi.|  
|[DDX_OCFloatRO](#ddx_ocfloatro)|Aktarımını yönetir **float** (veya **çift**) OLE denetimi bir salt okunur özelliği arasında veri ve **float** (veya **çift**) verileri üye.|  
|[Ddx_ocınt](#ddx_ocint)|Aktarımını yönetir `int` (veya **uzun**) OLE denetimi özelliği arasında veri ve bir `int` (veya **uzun**) veri üyesi.|  
|[Ddx_ocıntro](#ddx_ocintro)|Aktarımını yönetir `int` (veya **uzun**) OLE denetimi bir salt okunur özelliği arasında veri ve bir `int` (veya **uzun**) veri üyesi.|  
|[DDX_OCShort](#ddx_ocshort)|Aktarımını yönetir **kısa** OLE denetimi özelliği arasında veri ve **kısa** veri üyesi.|  
|[DDX_OCShortRO](#ddx_ocshortro)|Aktarımını yönetir **kısa** OLE denetimi bir salt okunur özelliği arasında veri ve **kısa** veri üyesi.|  
|[DDX_OCText](#ddx_octext)|Aktarımını yönetir **CString** OLE denetimi özelliği arasında veri ve **CString** veri üyesi.|  
|[DDX_OCTextRO](#ddx_octextro)|Aktarımını yönetir **CString** OLE denetimi bir salt okunur özelliği arasında veri ve **CString** veri üyesi.|  
  
##  <a name="ddx_ocbool"></a>DDX_OCBool  
 `DDX_OCBool` İşlevi aktarımını yönetir **BOOL** bir iletişim kutusu OLE denetimindeki bir özelliği arasında veri form görünümü ya da Denetim Görünüm nesnesi ve **BOOL** iletişim kutusu, form görünümü veri üyesi veya Denetim Görünüm nesnesi.  
  
```   
void AFXAPI DDX_OCBool(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    BOOL& value);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir `CDataExchange` nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 `nIDC`  
 OLE denetimi iletişim kutusunda, form görünümü veya denetim görünüm nesnesi kimliği.  
  
 `dispid`  
 Denetimin özelliğini gönderme kimliği.  
  
 *value*  
 İletişim kutusu, form görünümü veya denetim üye değişkeni bir başvuru veri değişimi nesne görüntüleyin.  
  
### <a name="remarks"></a>Açıklamalar  
 DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Başlık:** afxdisp.h  
  
##  <a name="ddx_ocboolro"></a>DDX_OCBoolRO  
 `DDX_OCBoolRO` İşlevi aktarımını yönetir **BOOL** bir iletişim kutusu OLE denetimindeki bir salt okunur özelliği arasında veri form görünümü ya da Denetim Görünüm nesnesi ve **BOOL** iletişim kutusunun veri üyesi Form görünümünde veya denetim görünüm nesnesi.  
  
```   
void AFXAPI DDX_OCBoolRO(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    BOOL& value);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir `CDataExchange` nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 `nIDC`  
 OLE denetimi iletişim kutusunda, form görünümü veya denetim görünüm nesnesi kimliği.  
  
 `dispid`  
 Denetimin özelliğini gönderme kimliği.  
  
 *value*  
 İletişim kutusu, form görünümü veya denetim üye değişkeni bir başvuru veri değişimi nesne görüntüleyin.  
  
### <a name="remarks"></a>Açıklamalar  
 DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdisp.h  
  
##  <a name="ddx_occolor"></a>DDX_OCColor  
 `DDX_OCColor` İşlevi aktarımını yönetir **OLE_COLOR** bir iletişim kutusu OLE denetimindeki bir özelliği arasında veri form görünümü ya da Denetim Görünüm nesnesi ve **OLE_COLOR** iletişim kutusunun veri üyesi Form görünümünde veya denetim görünüm nesnesi.  
  
```   
void AFXAPI DDX_OCColor(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    OLE_COLOR& value);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir `CDataExchange` nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 `nIDC`  
 OLE denetimi iletişim kutusunda, form görünümü veya denetim görünüm nesnesi kimliği.  
  
 `dispid`  
 Denetimin özelliğini gönderme kimliği.  
  
 *value*  
 İletişim kutusu, form görünümü veya denetim üye değişkeni bir başvuru veri değişimi nesne görüntüleyin.  
  
### <a name="remarks"></a>Açıklamalar  
 DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdisp.h  
  
##  <a name="ddx_occolorro"></a>DDX_OCColorRO  
 `DDX_OCColorRO` İşlevi aktarımını yönetir **OLE_COLOR** bir iletişim kutusu OLE denetimindeki bir salt okunur özelliği arasında veri form görünümü ya da Denetim Görünüm nesnesi ve **OLE_COLOR** veri üyesi iletişim kutusunda, form görünümü veya denetim görünüm nesnesi.  
  
```   
void AFXAPI DDX_OCColorRO(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    OLE_COLOR& value);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir `CDataExchange` nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 `nIDC`  
 OLE denetimi iletişim kutusunda, form görünümü veya denetim görünüm nesnesi kimliği.  
  
 `dispid`  
 Denetimin özelliğini gönderme kimliği.  
  
 *value*  
 İletişim kutusu, form görünümü veya denetim üye değişkeni bir başvuru veri değişimi nesne görüntüleyin.  
  
### <a name="remarks"></a>Açıklamalar  
 DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdisp.h  
  
##  <a name="ddx_ocfloat"></a>DDX_OCFloat  
 `DDX_OCFloat` İşlevi aktarımını yönetir **float** (veya **çift**) arasında bir iletişim kutusu OLE denetimindeki özelliğinin verileri form görünümü ya da Denetim Görünüm nesnesi ve **float** (veya **çift**) veri üyesi iletişim kutusu, form görünümü ya da Denetim Görünüm nesnesi.  
  
```   
void AFXAPI DDX_OCFloat(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    float& value);

void AFXAPI DDX_OCFloat(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    double& value);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir `CDataExchange` nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 `nIDC`  
 OLE denetimi iletişim kutusunda, form görünümü veya denetim görünüm nesnesi kimliği.  
  
 `dispid`  
 Denetimin özelliğini gönderme kimliği.  
  
 *value*  
 İletişim kutusu, form görünümü veya denetim üye değişkeni bir başvuru veri değişimi nesne görüntüleyin.  
  
### <a name="remarks"></a>Açıklamalar  
 DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdisp.h  
  
##  <a name="ddx_ocfloatro"></a>DDX_OCFloatRO  
 `DDX_OCFloatRO` İşlevi aktarımını yönetir **float** (veya **çift**) arasında bir iletişim kutusu OLE denetimindeki bir salt okunur özelliği veri form görünümü ya da Denetim Görünüm nesnesi ve  **float** (veya **çift**) veri üyesi iletişim kutusu, form görünümü ya da Denetim Görünüm nesnesi.  
  
```   
void AFXAPI DDX_OCFloatRO(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    float& value);

void AFXAPI DDX_OCFloatRO(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    double& value);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir `CDataExchange` nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 `nIDC`  
 OLE denetimi iletişim kutusunda, form görünümü veya denetim görünüm nesnesi kimliği.  
  
 `dispid`  
 Denetimin özelliğini gönderme kimliği.  
  
 *value*  
 İletişim kutusu, form görünümü veya denetim üye değişkeni bir başvuru veri değişimi nesne görüntüleyin.  
  
### <a name="remarks"></a>Açıklamalar  
 DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdisp.h  
  
##  <a name="ddx_ocint"></a>Ddx_ocınt  
 `DDX_OCInt` İşlevi aktarımını yönetir `int` (veya **uzun**) arasında bir iletişim kutusu OLE denetimindeki özelliğinin verileri form görünümü ya da Denetim Görünüm nesnesi ve `int` (veya **uzun**) veri üyesi iletişim kutusu, form görünümü ya da Denetim Görünüm nesnesi.  
  
```   
void AFXAPI DDX_OCInt(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    int& value);

void AFXAPI DDX_OCInt(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    long& value);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir `CDataExchange` nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 `nIDC`  
 OLE denetimi iletişim kutusunda, form görünümü veya denetim görünüm nesnesi kimliği.  
  
 `dispid`  
 Denetimin özelliğini gönderme kimliği.  
  
 *value*  
 İletişim kutusu, form görünümü veya denetim üye değişkeni bir başvuru veri değişimi nesne görüntüleyin.  
  
### <a name="remarks"></a>Açıklamalar  
 DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdisp.h  
  
##  <a name="ddx_ocintro"></a>Ddx_ocıntro  
 `DDX_OCIntRO` İşlevi aktarımını yönetir `int` (veya **uzun**) arasında bir iletişim kutusu OLE denetimindeki bir salt okunur özelliği veri form görünümü ya da Denetim Görünüm nesnesi ve `int` (veya **uzun** ) veri üyesi iletişim kutusu, form görünümü ya da Denetim Görünüm nesnesi.  
  
```   
void AFXAPI DDX_OCIntRO(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    int& value);

void AFXAPI DDX_OCIntRO(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    long& value);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir `CDataExchange` nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 `nIDC`  
 OLE denetimi iletişim kutusunda, form görünümü veya denetim görünüm nesnesi kimliği.  
  
 `dispid`  
 Denetimin özelliğini gönderme kimliği.  
  
 *value*  
 İletişim kutusu, form görünümü veya denetim üye değişkeni bir başvuru veri değişimi nesne görüntüleyin.  
  
### <a name="remarks"></a>Açıklamalar  
 DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdisp.h  
  
##  <a name="ddx_ocshort"></a>DDX_OCShort  
 `DDX_OCShort` İşlevi iletişim kutusunda, form görünümü OLE denetimi özelliğinin arasında kısa veri aktarımını yönetir veya denetim görünüm nesnesi ve kısa veri üyesi iletişim kutusu, form görünümü ya da Denetim Görünüm nesnesi.  
  
```   
void AFXAPI DDX_OCShort(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    short& value);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir `CDataExchange` nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 `nIDC`  
 OLE denetimi iletişim kutusunda, form görünümü veya denetim görünüm nesnesi kimliği.  
  
 `dispid`  
 Denetimin özelliğini gönderme kimliği.  
  
 *value*  
 İletişim kutusu, form görünümü veya denetim üye değişkeni bir başvuru veri değişimi nesne görüntüleyin.  
  
### <a name="remarks"></a>Açıklamalar  
 DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdisp.h  
  
##  <a name="ddx_ocshortro"></a>DDX_OCShortRO  
 `DDX_OCShortRO` İşlevi iletişim kutusunda, form görünümü OLE denetiminin salt okunur bir özellik arasında kısa veri aktarımını yönetir veya denetim görünüm nesnesi ve kısa veri üyesi iletişim kutusu, form görünümü ya da Denetim Görünüm nesnesi.  
  
```   
void AFXAPI DDX_OCShortRO(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    short& value);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir `CDataExchange` nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 `nIDC`  
 OLE denetimi iletişim kutusunda, form görünümü veya denetim görünüm nesnesi kimliği.  
  
 `dispid`  
 Denetimin özelliğini gönderme kimliği.  
  
 *value*  
 İletişim kutusu, form görünümü veya denetim üye değişkeni bir başvuru veri değişimi nesne görüntüleyin.  
  
### <a name="remarks"></a>Açıklamalar  
 DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdisp.h  
  
##  <a name="ddx_octext"></a>DDX_OCText  
 **DDX_OCText** işlevi aktarımını yönetir **CString** bir iletişim kutusu OLE denetimindeki bir özelliği arasında veri form görünümü ya da Denetim Görünüm nesnesi ve **CString** veri iletişim kutusu, form görünümü veya denetim görünüm nesnesi üyesi.  
  
```   
void AFXAPI DDX_OCText(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    CString& value); 
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir **CDataExchange** nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 `nIDC`  
 OLE denetimi iletişim kutusunda, form görünümü veya denetim görünüm nesnesi kimliği.  
  
 `dispid`  
 Denetimin özelliğini gönderme kimliği.  
  
 *value*  
 İletişim kutusu, form görünümü veya denetim üye değişkeni bir başvuru veri değişimi nesne görüntüleyin.  
  
### <a name="remarks"></a>Açıklamalar  
 DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdisp.h  
  
##  <a name="ddx_octextro"></a>DDX_OCTextRO  
 `DDX_OCTextRO` İşlevi aktarımını yönetir `CString` bir iletişim kutusu OLE denetimindeki bir salt okunur özelliği arasında veri form görünümü ya da Denetim Görünüm nesnesi ve `CString` veri üyesi iletişim kutusu, form görünümü ya da Denetim Görünüm nesnesi.  
  
```  
void AFXAPI DDX_OCTextRO(
    CDataExchange* pDX,  
    int nIDC,  
    DISPID dispid,  
    CString& value); 
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir `CDataExchange` nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 `nIDC`  
 OLE denetimi iletişim kutusunda, form görünümü veya denetim görünüm nesnesi kimliği.  
  
 `dispid`  
 Denetimin özelliğini gönderme kimliği.  
  
 *value*  
 İletişim kutusu, form görünümü veya denetim üye değişkeni bir başvuru veri değişimi nesne görüntüleyin.  
  
### <a name="remarks"></a>Açıklamalar  
 DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).  

### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdisp.h
    
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)
