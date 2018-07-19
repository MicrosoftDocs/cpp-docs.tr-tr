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
ms.openlocfilehash: b3c3270f76c6231a669bcf848680793cc924391b
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37339003"
---
# <a name="property-pages-mfc"></a>Özellik Sayfaları (MFC)
Özellik sayfaları geçerli değerleri belirli OLE denetim özelliklerini görüntüleme ve düzenleme iletişim kutusu veri değişimi (DDX) dayalı bir veri eşleme mekanizması destekleyerek için özelleştirilebilir ve grafik bir arabirim görüntülenir.  
  
 Bu veri eşleme mekanizmasını OLE denetimi özellikler için özellik sayfası denetimleri eşler. Denetim özelliğinin değeri, özellik sayfası denetimi içeriğini ve durumu yansıtır. Tarafından belirtilen özellik sayfası denetimleri ve özellikleri arasındaki eşlemeyi **DDP_** işlevi çağırır özellik sayfa `DoDataExchange` üye işlevi. Bir listesi verilmiştir **DDP_** denetiminizin özellik sayfasını kullanarak girilen veri değişimi işlevleri:  
  
### <a name="property-page-data-transfer"></a>Özellik sayfası veri aktarımı  
  
|||  
|-|-|  
|[Ddp_cbındex](#ddp_cbindex)|Seçili dizenin dizininde bir birleşik giriş kutusu denetim özelliği ile bağlar.|  
|[DDP_CBString](#ddp_cbstring)|Bir denetimin bir özelliğine sahip bir birleşik giriş kutusunda seçili dizeyi bağlar. Seçili dizeyi özelliğinin değeri olarak aynı harfler ile başlayabilir, ancak tam olarak eşleşmesi gerekmez.|  
|[DDP_CBStringExact](#ddp_cbstringexact)|Bir denetimin bir özelliğine sahip bir birleşik giriş kutusunda seçili dizeyi bağlar. Seçili dizeyi ve özelliğinin dize değerini tam olarak eşleşmelidir.|  
|[DDP_Check](#ddp_check)|Bir denetimin özelliğiyle denetimin özellik sayfası'ndaki bir onay kutusu bağlar.|  
|[Ddp_lbındex](#ddp_lbindex)|Bir denetimin özelliği ile bir liste kutusunda seçili dizenin dizin bağlar.|  
|[DDP_LBString](#ddp_lbstring)|Bir denetimin özelliği ile bir liste kutusunda seçili dizeyi bağlar. Seçili dizeyi özelliğinin değeri olarak aynı harfler ile başlayabilir, ancak tam olarak eşleşen yok.|  
|[DDP_LBStringExact](#ddp_lbstringexact)|Bir denetimin özelliği ile bir liste kutusunda seçili dizeyi bağlar. Seçili dizeyi ve özelliğinin dize değerini tam olarak eşleşmelidir.|  
|[DDP_PostProcessing](#ddp_postprocessing)|Özellik değerleri, denetiminden aktarımı tamamlanır.|  
|[DDP_Radio](#ddp_radio)|Denetimin özellik sayfası bir denetim özelliğine sahip bir radyo düğmesi grubunda bağlar.|  
|[DDP_Text](#ddp_text)|Bir denetimin özelliğiyle denetimin özellik sayfası denetiminde bağlar. Bu işlev gibi özellikler, birkaç farklı türde işler **çift**, **kısa**, BSTR, ve **uzun**.|  
  
 Hakkında daha fazla bilgi için `DoDataExchange` işlevi ve özellik sayfaları makaleye göz atın [ActiveX denetimleri: özellik sayfaları](../../mfc/mfc-activex-controls-property-pages.md).  
  
 Makrolar oluşturmak ve yönetmek için bir OLE denetim özelliği sayfaları için kullanılan bir listesi verilmiştir:  
  
### <a name="property-pages"></a>Özellik Sayfaları  
  
|||  
|-|-|  
|[BEGIN_PROPPAGEIDS](#begin_proppageids)|Özellik sayfası kimlikleri listesini başlar.|  
|[END_PROPPAGEIDS](#end_proppageids)|Özellik sayfası kimlikleri listesini sona erer.|  
|[PROPPAGEID](#proppageid)|Bir özellik sayfası denetimi sınıf bildirir.|  
  
##  <a name="ddp_cbindex"></a>  Ddp_cbındex  
 Bu işlev, özellik sayfanın çağrı `DoDataExchange` tamsayı özellik değeri bir birleşik giriş kutusu özellik sayfasında bulunan geçerli seçime dizini ile eşitlemek için işlevi.  
  
```   
void AFXAPI DDP_CBIndex(
    CDataExchange* pDX,  
    int id,  
    int& member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>Parametreler  
 *pDX*  
 İşaretçi bir `CDataExchange` nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.  
  
 *id*  
 Kaynak Kimliğini birleşik giriş kutusu denetimi tarafından belirtilen denetim özelliği ile ilişkili *pszPropName*.  
  
 *Üyesi*  
 Üye değişkeni tarafından belirtilen özellik sayfası denetimi ile ilişkili *kimliği* ve tarafından belirtilen özellik *pszPropName*.  
  
 *pszPropName*  
 Denetim özelliği tarafından belirtilen birleşik giriş kutusu denetimi ile değiştirilecek özellik adı *kimliği*.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, karşılık gelen önce çağrılmalıdır `DDX_CBIndex` işlev çağrısı.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üst bilgi** afxctl.h  
  
##  <a name="ddp_cbstring"></a>  DDP_CBString  
 Bu işlev, özellik sayfanın çağrı `DoDataExchange` işlevi bir dize özelliğinin değeri bir birleşik giriş kutusu özellik sayfasında bulunan geçerli seçime eşitlenecek.  
  
```  
void AFXAPI DDP_CBString(
    CDataExchange* pDX,  
    int id,  
    CString& member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>Parametreler  
 *pDX*  
 İşaretçi bir `CDataExchange` nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.  
  
 *id*  
 Kaynak Kimliğini birleşik giriş kutusu denetimi tarafından belirtilen denetim özelliği ile ilişkili *pszPropName*.  
  
 *Üyesi*  
 Üye değişkeni tarafından belirtilen özellik sayfası denetimi ile ilişkili *kimliği* ve tarafından belirtilen özellik *pszPropName*.  
  
 *pszPropName*  
 Denetim özelliği tarafından belirtilen birleşik giriş kutusu dizeyle değiştirilecek özellik adı *kimliği*.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, karşılık gelen önce çağrılmalıdır `DDX_CBString` işlev çağrısı.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üst bilgi** afxctl.h  
  
##  <a name="ddp_cbstringexact"></a>  DDP_CBStringExact  
 Bu işlev, özellik sayfanın çağrı `DoDataExchange` bir birleşik giriş kutusu özellik sayfasında bulunan geçerli seçime tam olarak eşleşen bir dize özelliği değeri eşitlemek için işlevi.  
  
```  
void AFXAPI DDP_CBStringExact(
    CDataExchange* pDX,  
    int id,  
    CString& member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>Parametreler  
 *pDX*  
 İşaretçi bir `CDataExchange` nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.  
  
 *id*  
 Kaynak Kimliğini birleşik giriş kutusu denetimi tarafından belirtilen denetim özelliği ile ilişkili *pszPropName*.  
  
 *Üyesi*  
 Üye değişkeni tarafından belirtilen özellik sayfası denetimi ile ilişkili *kimliği* ve tarafından belirtilen özellik *pszPropName*.  
  
 *pszPropName*  
 Denetim özelliği tarafından belirtilen birleşik giriş kutusu dizeyle değiştirilecek özellik adı *kimliği*.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, karşılık gelen önce çağrılmalıdır `DDX_CBStringExact` işlev çağrısı.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üst bilgi** afxctl.h  
  
##  <a name="ddp_check"></a>  DDP_Check  
 Bu işlev, özellik sayfanın çağrı `DoDataExchange` özelliğinin değeri ile ilişkili özellik sayfası onay kutusu denetimi eşitlemek için işlevi.  
  
```   
void AFXAPI DDP_Check(
    CDataExchange* pDX,  
    int id,  
    int & member,  
    LPCSTR pszPropName);
```  
  
### <a name="parameters"></a>Parametreler  
 *pDX*  
 İşaretçi bir `CDataExchange` nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.  
  
 *id*  
 Onay kutusu denetimi kaynak kimliği tarafından belirtilen denetim özelliği ilişkili *pszPropName*.  
  
 *Üyesi*  
 Üye değişkeni tarafından belirtilen özellik sayfası denetimi ile ilişkili *kimliği* ve tarafından belirtilen özellik *pszPropName*.  
  
 *pszPropName*  
 Denetim özelliği tarafından belirtilen onay kutusu denetimi ile değiştirilecek özellik adı *kimliği*.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, karşılık gelen önce çağrılmalıdır `DDX_Check` işlev çağrısı.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üst bilgi** afxctl.h  
  
##  <a name="ddp_lbindex"></a>  Ddp_lbındex  
 Bu işlevi çağırın, özellik sayfanın `DoDataExchange` bir liste kutusu özellik sayfasında geçerli seçimde'nün dizinine sahip bir tamsayı özelliği değeri eşitlemek için işlevi.  
  
```   
void AFXAPI DDP_LBIndex(
    CDataExchange* pDX,  
    int id,  
    int& member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>Parametreler  
 *pDX*  
 İşaretçi bir `CDataExchange` nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.  
  
 *id*  
 Kaynak Kimliği listesi denetimi tarafından belirtilen denetim özelliği ile ilişkili kutusuna *pszPropName*.  
  
 *Üyesi*  
 Üye değişkeni tarafından belirtilen özellik sayfası denetimi ile ilişkili *kimliği* ve tarafından belirtilen özellik *pszPropName*.  
  
 *pszPropName*  
 Denetim özelliği tarafından belirtilen liste kutusu dizeyle değiştirilecek özellik adı *kimliği*.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, karşılık gelen önce çağrılmalıdır `DDX_LBIndex` işlev çağrısı.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üst bilgi** afxctl.h  
  
##  <a name="ddp_lbstring"></a>  DDP_LBString  
 Bu işlev, özellik sayfanın çağrı `DoDataExchange` işlevi bir dize özelliğinin değeri bir liste kutusu özellik sayfasında bulunan geçerli seçime eşitlenecek.  
  
```   
void AFXAPI DDP_LBString(
    CDataExchange* pDX,  
    int id,  
    CString& member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>Parametreler  
 *pDX*  
 İşaretçi bir `CDataExchange` nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.  
  
 *id*  
 Kaynak Kimliği listesi denetimi tarafından belirtilen denetim özelliği ile ilişkili kutusuna *pszPropName*.  
  
 *Üyesi*  
 Üye değişkeni tarafından belirtilen özellik sayfası denetimi ile ilişkili *kimliği* ve tarafından belirtilen özellik *pszPropName*.  
  
 *pszPropName*  
 Denetim özelliği tarafından belirtilen liste kutusu dizeyle değiştirilecek özellik adı *kimliği*.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, karşılık gelen önce çağrılmalıdır `DDX_LBString` işlev çağrısı.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üst bilgi** afxctl.h  
  
##  <a name="ddp_lbstringexact"></a>  DDP_LBStringExact  
 Bu işlev, özellik sayfanın çağrı `DoDataExchange` geçerli seçim liste kutusu özellik sayfasında, tam olarak eşleşen bir dize özelliği değeri eşitlemek için işlevi.  
  
```   
void AFXAPI DDP_LBStringExact(
    CDataExchange* pDX,  
    int id,  
    CString& member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>Parametreler  
 *pDX*  
 İşaretçi bir `CDataExchange` nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.  
  
 *id*  
 Kaynak Kimliği listesi denetimi tarafından belirtilen denetim özelliği ile ilişkili kutusuna *pszPropName*.  
  
 *Üyesi*  
 Üye değişkeni tarafından belirtilen özellik sayfası denetimi ile ilişkili *kimliği* ve tarafından belirtilen özellik *pszPropName*.  
  
 *pszPropName*  
 Denetim özelliği tarafından belirtilen liste kutusu dizeyle değiştirilecek özellik adı *kimliği*.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, karşılık gelen önce çağrılmalıdır `DDX_LBStringExact` işlev çağrısı.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üst bilgi** afxctl.h  
  
##  <a name="ddp_postprocessing"></a>  DDP_PostProcessing  
 Bu işlev, özellik sayfanın çağrı `DoDataExchange` özellik değerlerini kaydedildiğinde denetiminiz özellik sayfasından özellik değerlerini aktarılmasını tamamlamak için işlevi.  
  
```   
void AFXAPI DDP_PostProcessing(CDataExchange * pDX);
```  
  
### <a name="parameters"></a>Parametreler  
 *pDX*  
 İşaretçi bir `CDataExchange` nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, tüm veri değişimi işlevleri tamamlandıktan sonra çağrılmalıdır. Örneğin:  
  
 [!code-cpp[NVC_MFCAxCtl#15](../../mfc/reference/codesnippet/cpp/property-pages-mfc_1.cpp)]  
  
### <a name="requirements"></a>Gereksinimler  
  **Üst bilgi** afxctl.h  
  
##  <a name="ddp_radio"></a>  DDP_Radio  
 Denetiminizin içinde bu işlevi çağırın `DoPropExchange` özelliğinin değeri ile ilişkili özellik sayfası radyo düğmesi denetimini eşitlemek için işlevi.  
  
```   
void AFXAPI DDP_Radio(
    CDataExchange* pDX,  
    int id,  
    int & member,  
    LPCTSTR pszPropName);
```  
  
### <a name="parameters"></a>Parametreler  
 *pDX*  
 İşaretçi bir `CDataExchange` nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.  
  
 *id*  
 Kaynak Kimliği radyo düğmesi denetimi tarafından belirtilen denetim özelliği ile ilişkili *pszPropName*.  
  
 *Üyesi*  
 Üye değişkeni tarafından belirtilen özellik sayfası denetimi ile ilişkili *kimliği* ve tarafından belirtilen özellik *pszPropName*.  
  
 *pszPropName*  
 Denetim özelliği tarafından belirtilen radyo düğmesi denetimini öğesiyle değiştirilecek özellik adı *kimliği*.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, karşılık gelen önce çağrılmalıdır `DDX_Radio` işlev çağrısı.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üst bilgi** afxctl.h  
  
##  <a name="ddp_text"></a>  DDP_Text  
 Denetiminizin içinde bu işlevi çağırın `DoDataExchange` özelliğinin değeri ile ilişkili özellik sayfası denetimi eşitlemek için işlevi.  
  
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
 *pDX*  
 İşaretçi bir `CDataExchange` nesne. Framework yön dahil olmak üzere veri değişimi bağlamında kurmak için bu nesneyi sağlar.  
  
 *id*  
 Kaynak Kimliği tarafından belirtilen denetim özelliği ile ilişkili denetim *pszPropName*.  
  
 *Üyesi*  
 Üye değişkeni tarafından belirtilen özellik sayfası denetimi ile ilişkili *kimliği* ve tarafından belirtilen özellik *pszPropName*.  
  
 *pszPropName*  
 Denetim özelliği tarafından belirtilen denetim öğesiyle değiştirilecek özellik adı *kimliği*.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, karşılık gelen önce çağrılmalıdır `DDX_Text` işlev çağrısı.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üst bilgi** afxctl.h  
  
##  <a name="begin_proppageids"></a>  BEGIN_PROPPAGEIDS  
 Denetimin özellik sayfası kimlikleri listesi tanımını başlar.  
  
```   
BEGIN_PROPPAGEIDS(class_name,  count)   
```  
  
### <a name="parameters"></a>Parametreler  
 *$class_name*  
 Sayfaları hangi özelliği için belirtilen denetim sınıfı adı.  
  
 *Sayısı*  
 Özellik sayfaları denetim sınıf tarafından kullanılan sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Sınıfınız için üye işlevleri tanımlayan uygulama dosyasında (.cpp), özellik sayfasında listesini begın_proppageıds makrosu ile Başlat sonra her biri, özellik sayfaları için makro girişler ekleyin ve end_proppageıds özellik sayfası listesiyle tamamlayın Makro.  
  
 Özellik sayfaları hakkında daha fazla bilgi için bkz [ActiveX denetimleri: özellik sayfaları](../../mfc/mfc-activex-controls-property-pages.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üst bilgi** afxctl.h  
  
##  <a name="end_proppageids"></a>  END_PROPPAGEIDS  
 Özellik sayfası kimliği listenize tanımını sonlandırır.  
  
```   
END_PROPPAGEIDS(class_name)   
```  
  
### <a name="parameters"></a>Parametreler  
 *$class_name*  
 Özellik sayfasını sahibi denetim sınıfı adı.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üst bilgi** afxctl.h  
  
##  <a name="proppageid"></a>  PROPPAGEID  
 OLE denetiminizi kullanmak için bir özellik sayfası ekler.  
  
```   
PROPPAGEID(clsid)   
```  
  
### <a name="parameters"></a>Parametreler  
 *CLSID*  
 Özellik sayfası sınıfı benzersiz kimliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm PROPPAGEID makroları denetiminizin uygulamasını dosyadaki begın_proppageıds ve end_proppageıds makrolar arasında yerleştirilmelidir.  

### <a name="requirements"></a>Gereksinimler  
  **Üst bilgi** afxctl.h  
    
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)
