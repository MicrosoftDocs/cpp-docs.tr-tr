---
title: Özellik sayfaları (MFC) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- property page data transfer functions in MFC
- property pages [MFC], global MFC functions
ms.assetid: 734f88bc-c776-4136-9b0e-f45c761a45c1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0895cd22870b3a4a266e9be12f0000fae7f7101a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="property-pages-mfc"></a>Özellik Sayfaları (MFC)
Özellik sayfaları görüntüleme ve düzenleme iletişim kutusu veri değişimi (DDX) dayalı bir veri eşleme mekanizması destekleyerek için özelleştirilebilir, grafik bir arabirim belirli OLE denetim özellikleri geçerli değerlerini görüntüler.  
  
 Bu veri eşleme mekanizması OLE denetimi ayrı ayrı özellikler için özellik sayfası denetimleri eşler. Denetim özelliğinin değeri durumu veya özellik sayfası denetimi içeriğini yansıtır. Özellik sayfası denetimleri ve özellikleri arasında eşleme tarafından belirtilen **DDP_** işlevi çağırır özelliği sayfanın `DoDataExchange` üye işlevi. Bir listesi aşağıda verilmiştir **DDP_** denetiminizin özellik sayfası kullanılarak girilen veri değişimi işlevleri:  
  
### <a name="property-page-data-transfer"></a>Özellik sayfası veri aktarımı  
  
|||  
|-|-|  
|[Ddp_cbındex](#ddp_cbindex)|Birleşik giriş kutusu denetim özelliğiyle seçili dizesinin dizinde bağlar.|  
|[DDP_CBString](#ddp_cbstring)|Birleşik giriş kutusu denetim özelliğiyle seçili dizesinde bağlar. Seçili dizeyi özelliğin değerini aynı harflerle başlayabilir ancak tam olarak eşleşmesi gerekmez.|  
|[DDP_CBStringExact](#ddp_cbstringexact)|Birleşik giriş kutusu denetim özelliğiyle seçili dizesinde bağlar. Seçili dizeyi ve özelliğin dize değeri tam olarak eşleşmelidir.|  
|[DDP_Check](#ddp_check)|Denetimin özellik sayfası bir denetimin özelliğiyle onay kutusuna bağlar.|  
|[Ddp_lbındex](#ddp_lbindex)|Bir denetimin özelliğine sahip bir liste kutusunda seçili dizesinin dizin bağlar.|  
|[DDP_LBString](#ddp_lbstring)|Bir denetimin özelliğine sahip bir liste kutusunda seçili dizeyi bağlar. Seçili dizeyi özelliğin değerini aynı harflerle başlayabilir ancak onu tam olarak eşleşmiyor.|  
|[DDP_LBStringExact](#ddp_lbstringexact)|Bir denetimin özelliğine sahip bir liste kutusunda seçili dizeyi bağlar. Seçili dizeyi ve özelliğin dize değeri tam olarak eşleşmelidir.|  
|[DDP_PostProcessing](#ddp_postprocessing)|Denetim özellik değerlerinin aktarımı tamamlanır.|  
|[DDP_Radio](#ddp_radio)|Bir denetimin özellik sayfası bir denetimin özelliğiyle radyo düğmesi grubunda bağlantılar.|  
|[DDP_Text](#ddp_text)|Denetimin özellik sayfasında bir denetimin özelliğiyle denetimindeki bağlar. Bu işlev özellikleri, birkaç farklı türde gibi işler **çift**, **kısa**, `BSTR`, ve **uzun**.|  
  
 Hakkında daha fazla bilgi için `DoDataExchange` işlevi ve özellik sayfaları makalesine bakın [ActiveX denetimleri: özellik sayfaları](../../mfc/mfc-activex-controls-property-pages.md).  
  
 Makroları oluşturmak ve özellik sayfaları için bir OLE denetimi yönetmek için kullanılan bir listesi verilmiştir:  
  
### <a name="property-pages"></a>Özellik Sayfaları  
  
|||  
|-|-|  
|[BEGIN_PROPPAGEIDS](#begin_proppageids)|Özellik sayfası kimlikleri listesini başlar.|  
|[END_PROPPAGEIDS](#end_proppageids)|Özellik sayfası kimlikleri listesini sona erer.|  
|[PROPPAGEID](#proppageid)|Denetim sınıfı bir özellik sayfasında bildirir.|  
  
##  <a name="ddp_cbindex"></a>  Ddp_cbındex  
 Bu işlev, özellik sayfanın çağrı `DoDataExchange` birleşik giriş kutusu özellik sayfasında bulunan geçerli seçime dizini bir tamsayı özelliği değeri eşitlemek için işlev.  
  
```   
void AFXAPI DDP_CBIndex(
    CDataExchange* pDX,  
    int id,  
    int& member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 İşaretçi bir `CDataExchange` nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 `id`  
 Birleşik giriş kaynak Kimliğini kutusu tarafından belirtilen denetim özelliği ile ilişkili denetim `pszPropName`.  
  
 `member`  
 Üye değişkeni tarafından belirtilen özellik sayfası denetimi ile ilişkili `id` ve tarafından belirtilen özellik `pszPropName`.  
  
 `pszPropName`  
 Tarafından belirtilen birleşik giriş kutusu denetimi ile değiştirilmek üzere Denetim özelliğin özellik adını `id`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, karşılık gelen önce çağrılmalıdır `DDX_CBIndex` işlev çağrısı.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxctl.h  
  
##  <a name="ddp_cbstring"></a>  DDP_CBString  
 Bu işlev, özellik sayfanın çağrı `DoDataExchange` dize özelliğinin değeri bir birleşik giriş kutusu özellik sayfasında geçerli seçim ile eşitlemek için işlevi.  
  
```  
void AFXAPI DDP_CBString(
    CDataExchange* pDX,  
    int id,  
    CString& member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 İşaretçi bir `CDataExchange` nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 `id`  
 Birleşik giriş kaynak Kimliğini kutusu tarafından belirtilen denetim özelliği ile ilişkili denetim `pszPropName`.  
  
 `member`  
 Üye değişkeni tarafından belirtilen özellik sayfası denetimi ile ilişkili `id` ve tarafından belirtilen özellik `pszPropName`.  
  
 `pszPropName`  
 Birleşik giriş kutusu dizesi tarafından belirtilen ile değiştirilmek üzere Denetim özelliğin özellik adını `id`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, karşılık gelen önce çağrılmalıdır `DDX_CBString` işlev çağrısı.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxctl.h  
  
##  <a name="ddp_cbstringexact"></a>  DDP_CBStringExact  
 Bu işlev, özellik sayfanın çağrı `DoDataExchange` işlevi tam olarak bir birleşik giriş kutusu özellik sayfasında bulunan geçerli seçime eşleşen bir dize özelliği değerini eşitlenecek.  
  
```  
void AFXAPI DDP_CBStringExact(
    CDataExchange* pDX,  
    int id,  
    CString& member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 İşaretçi bir `CDataExchange` nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 `id`  
 Birleşik giriş kaynak Kimliğini kutusu tarafından belirtilen denetim özelliği ile ilişkili denetim `pszPropName`.  
  
 `member`  
 Üye değişkeni tarafından belirtilen özellik sayfası denetimi ile ilişkili `id` ve tarafından belirtilen özellik `pszPropName`.  
  
 `pszPropName`  
 Birleşik giriş kutusu dizesi tarafından belirtilen ile değiştirilmek üzere Denetim özelliğin özellik adını `id`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, karşılık gelen önce çağrılmalıdır `DDX_CBStringExact` işlev çağrısı.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxctl.h  
  
##  <a name="ddp_check"></a>  DDP_Check  
 Bu işlev, özellik sayfanın çağrı `DoDataExchange` işlevi özelliğinin değeri ilişkili özellik sayfası onay kutusu denetimi ile eşitleyin.  
  
```   
void AFXAPI DDP_Check(
    CDataExchange* pDX,  
    int id,  
    int & member,  
    LPCSTR pszPropName);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 İşaretçi bir `CDataExchange` nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 `id`  
 Onay kutusu denetimi kaynak kimliği tarafından belirtilen denetim özelliği ile ilişkili `pszPropName`.  
  
 `member`  
 Üye değişkeni tarafından belirtilen özellik sayfası denetimi ile ilişkili `id` ve tarafından belirtilen özellik `pszPropName`.  
  
 `pszPropName`  
 Tarafından belirtilen onay kutusu denetimi ile değiştirilmek üzere Denetim özelliğin özellik adını `id`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, karşılık gelen önce çağrılmalıdır `DDX_Check` işlev çağrısı.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxctl.h  
  
##  <a name="ddp_lbindex"></a>  Ddp_lbındex  
 Bu işlev, özellik sayfanın çağrı `DoDataExchange` bir tamsayı özelliğinin değeri bir liste kutusu özellik sayfasında bulunan geçerli seçime dizini ile eşitlemek için işlevi.  
  
```   
void AFXAPI DDP_LBIndex(
    CDataExchange* pDX,  
    int id,  
    int& member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 İşaretçi bir `CDataExchange` nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 `id`  
 Kaynak kimliği listesinin kutusu tarafından belirtilen denetim özelliği ile ilişkili denetim `pszPropName`.  
  
 `member`  
 Üye değişkeni tarafından belirtilen özellik sayfası denetimi ile ilişkili `id` ve tarafından belirtilen özellik `pszPropName`.  
  
 `pszPropName`  
 Belirtilen liste kutusunu dizesiyle değiştirilmek üzere Denetim özelliğin özellik adını `id`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, karşılık gelen önce çağrılmalıdır `DDX_LBIndex` işlev çağrısı.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxctl.h  
  
##  <a name="ddp_lbstring"></a>  DDP_LBString  
 Bu işlev, özellik sayfanın çağrı `DoDataExchange` dize özelliğinin değeri bir liste kutusu özellik sayfasında geçerli seçim ile eşitlemek için işlevi.  
  
```   
void AFXAPI DDP_LBString(
    CDataExchange* pDX,  
    int id,  
    CString& member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 İşaretçi bir `CDataExchange` nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 `id`  
 Kaynak kimliği listesinin kutusu tarafından belirtilen denetim özelliği ile ilişkili denetim `pszPropName`.  
  
 `member`  
 Üye değişkeni tarafından belirtilen özellik sayfası denetimi ile ilişkili `id` ve tarafından belirtilen özellik `pszPropName`.  
  
 `pszPropName`  
 Belirtilen liste kutusunu dizesiyle değiştirilmek üzere Denetim özelliğin özellik adını `id`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, karşılık gelen önce çağrılmalıdır `DDX_LBString` işlev çağrısı.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxctl.h  
  
##  <a name="ddp_lbstringexact"></a>  DDP_LBStringExact  
 Bu işlev, özellik sayfanın çağrı `DoDataExchange` özellik sayfasında liste kutusunda geçerli seçim ile tam olarak bir dize özelliği değeri eşitlemek için işlevi.  
  
```   
void AFXAPI DDP_LBStringExact(
    CDataExchange* pDX,  
    int id,  
    CString& member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 İşaretçi bir `CDataExchange` nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 `id`  
 Kaynak kimliği listesinin kutusu tarafından belirtilen denetim özelliği ile ilişkili denetim `pszPropName`.  
  
 `member`  
 Üye değişkeni tarafından belirtilen özellik sayfası denetimi ile ilişkili `id` ve tarafından belirtilen özellik `pszPropName`.  
  
 `pszPropName`  
 Belirtilen liste kutusunu dizesiyle değiştirilmek üzere Denetim özelliğin özellik adını `id`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, karşılık gelen önce çağrılmalıdır `DDX_LBStringExact` işlev çağrısı.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxctl.h  
  
##  <a name="ddp_postprocessing"></a>  DDP_PostProcessing  
 Bu işlev, özellik sayfanın çağrı `DoDataExchange` özellik değerlerini kaydedildiğinde denetiminizi özellik sayfasından özellik değerlerini aktarımını tamamlanması işlevi.  
  
```   
void AFXAPI DDP_PostProcessing(CDataExchange * pDX);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 İşaretçi bir `CDataExchange` nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm veri değişimi işlevleri tamamlandıktan sonra bu işlev çağrılmalıdır. Örneğin:  
  
 [!code-cpp[NVC_MFCAxCtl#15](../../mfc/reference/codesnippet/cpp/property-pages-mfc_1.cpp)]  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxctl.h  
  
##  <a name="ddp_radio"></a>  DDP_Radio  
 Denetim içinde bu işlevi çağırmak `DoPropExchange` özelliğinin değeri ile ilişkili özellik sayfası radyo düğmesi denetimini eşitlemek için işlevi.  
  
```   
void AFXAPI DDP_Radio(
    CDataExchange* pDX,  
    int id,  
    int & member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 İşaretçi bir `CDataExchange` nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 `id`  
 Kaynak Kimliği radyo düğmesi denetim tarafından belirtilen denetim özelliği ile ilişkili `pszPropName`.  
  
 `member`  
 Üye değişkeni tarafından belirtilen özellik sayfası denetimi ile ilişkili `id` ve tarafından belirtilen özellik `pszPropName`.  
  
 `pszPropName`  
 Tarafından belirtilen radyo düğmesi denetimini ile değiştirilmek üzere Denetim özelliğin özellik adını `id`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, karşılık gelen önce çağrılmalıdır `DDX_Radio` işlev çağrısı.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxctl.h  
  
##  <a name="ddp_text"></a>  DDP_Text  
 Denetim içinde bu işlevi çağırmak `DoDataExchange` özelliğinin değeri ile ilişkili özellik sayfası denetimi eşitlemek için işlevi.  
  
```   
void AFXAPI DDP_Text(
    CDataExchange* pDX,  
    int id,  
    BYTE & member,  
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,  
    int id,  
    int & member,  
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,  
    int id,  
    UINT & member,  
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,  
    int id,  
    long & member,  
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,  
    int id,  
    DWORD & member,  
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,  
    int id,  
    float & member,  
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,  
    int id,  
    double & member,  
    LPCTSTR pszPropName);

void AFXAPI DDP_Text(
    CDataExchange* pDX,  
    int id,  
    CString & member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 İşaretçi bir `CDataExchange` nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 `id`  
 Kaynak Kimliği tarafından belirtilen denetim özelliği ile ilişkili denetiminin `pszPropName`.  
  
 `member`  
 Üye değişkeni tarafından belirtilen özellik sayfası denetimi ile ilişkili `id` ve tarafından belirtilen özellik `pszPropName`.  
  
 `pszPropName`  
 Tarafından belirtilen denetimiyle değiştirilmek üzere Denetim özelliğin özellik adını `id`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, karşılık gelen önce çağrılmalıdır `DDX_Text` işlev çağrısı.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxctl.h  
  
##  <a name="begin_proppageids"></a>  BEGIN_PROPPAGEIDS  
 Özellik sayfası kimlikleri denetiminizin listesi tanımını başlar.  
  
```   
BEGIN_PROPPAGEIDS(class_name,  count)   
```  
  
### <a name="parameters"></a>Parametreler  
 *class_name*  
 Sayfaları hangi özelliği için belirtilen control sınıfı adı.  
  
 *Sayısı*  
 Denetim sınıfı tarafından kullanılan özellik sayfaları sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Özellik sayfası listesiyle sınıfınız için üye işlevleri tanımlar uygulaması (.cpp) dosyasına Başlat `BEGIN_PROPPAGEIDS` makrosu, ardından her bir özellik sayfaları için makrosu girişleri ekleyin ve özellik sayfası listesiyle tamamlamak `END_PROPPAGEIDS` makrosu.  
  
 Özellik sayfaları hakkında daha fazla bilgi için bkz: [ActiveX denetimleri: özellik sayfaları](../../mfc/mfc-activex-controls-property-pages.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxctl.h  
  
##  <a name="end_proppageids"></a>  END_PROPPAGEIDS  
 Özellik sayfası kimliği listenize tanımını sona erer.  
  
```   
END_PROPPAGEIDS(class_name)   
```  
  
### <a name="parameters"></a>Parametreler  
 *class_name*  
 Özellik sayfası sahibi control sınıfı adı.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxctl.h  
  
##  <a name="proppageid"></a>  PROPPAGEID  
 OLE denetim tarafından kullanım için bir özellik sayfası ekler.  
  
```   
PROPPAGEID(clsid)   
```  
  
### <a name="parameters"></a>Parametreler  
 `clsid`  
 Özellik sayfası benzersiz sınıf kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm `PROPPAGEID` makroları yerleştirildiğinde, arasında `BEGIN_PROPPAGEIDS` ve `END_PROPPAGEIDS` denetiminizin uygulama dosyadaki makrolar.  

### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxctl.h  
    
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)
