---
title: "CRecordView ve CDaoRecordView için iletişim kutusu veri değişimi işlevleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AFXDAO/DDX_FieldCBIndex
- AFXDAO/DDX_FieldCBString
- AFXDAO/DDX_FieldCBStringExact
- AFXDAO/DDX_FieldCheck
- AFXDAO/DDX_FieldLBIndex
- AFXDAO/DDX_FieldLBString
- AFXDAO/DDX_FieldLBStringExact
- AFXDAO/DDX_FieldRadio
- AFXDAO/DDX_FieldScroll
- AFXDAO/DDX_FieldText
dev_langs:
- C++
helpviewer_keywords:
- DDX_Field functions [MFC]
- ODBC [MFC], dialog data exchange (DDX) support
- DDX (dialog data exchange) [MFC], database support
- DDX (dialog data exchange) [MFC], functions
- databases [MFC], dialog data exchange (DDX) support
- DAO [MFC], dialog data exchange (DDX) support
ms.assetid: 0d8cde38-3a2c-4100-9589-ac80a7b1ce91
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f58b7ba7ae51c4db065cd7b30cc233128f7b7c68
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="dialog-data-exchange-functions-for-crecordview-and-cdaorecordview"></a>CRecordView ve CDaoRecordView için İletişim Kutusu Veri Değişimi İşlevleri
Bu konu arasında veri değişimi için kullanılan DDX_Field işlevleri listeler bir [CRecordset](../../mfc/reference/crecordset-class.md) ve [CRecordView](../../mfc/reference/crecordview-class.md) form veya bir [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) ve [ CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) formu.  
  
> [!NOTE]
>  Formdaki denetimleri ile veri değişimi DDX_Field işlevleri gibi DDX işlevleri bir seçenektir. Ancak DDX farklı olarak, bunlar görünümün ilişkili kayıt kümesi nesnesi alanlarla yerine kayıt görünümü alanlarının ile veri değişimi. Daha fazla bilgi için bkz: sınıfları `CRecordView` ve `CDaoRecordView`.  
  
### <a name="ddxfield-functions"></a>DDX_Field işlevleri  
  
|||  
|-|-|  
|[Ddx_fieldcbındex](#ddx_fieldcbindex)|Kayıt kümesi alan veri üyesi ve açılan kutuda geçerli seçim dizin arasında tamsayı veri aktarımı yapan bir [CRecordView](../../mfc/reference/crecordview-class.md) veya [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md).|  
|[DDX_FieldCBString](#ddx_fieldcbstring)|Aktarımları `CString` kayıt kümesi alan veri üyesi ve bir birleşik düzen denetimi arasında veri kutusunda bir `CRecordView` veya `CDaoRecordView`. Veri denetime kayıt kümesinden taşırken, bu işlev öğesi karakter belirtilen dize ile başlayan birleşik giriş kutusunu seçer.|  
|[DDX_FieldCBStringExact](#ddx_fieldcbstringexact)|Aktarımları `CString` kayıt kümesi alan veri üyesi ve bir birleşik düzen denetimi arasında veri kutusunda bir `CRecordView` veya `CDaoRecordView`. Veri denetime kayıt kümesinden taşırken, bu işlev öğesi belirtilen dize ile tam olarak açılan kutuda seçer.|  
|[DDX_FieldCheck](#ddx_fieldcheck)|Kayıt kümesi alan veri üyesi ve onay kutusuna arasında Boole veri aktarımı yapan bir `CRecordView` veya `CDaoRecordView`.|  
|[Ddx_fieldlbındex](#ddx_fieldlbindex)|Kayıt kümesi alan veri üyesi ve bir liste kutusunda bulunan geçerli seçime dizin arasında tamsayı veri aktarımı yapan bir `CRecordView` veya `CDaoRecordView`.|  
|[DDX_FieldLBString](#ddx_fieldlbstring)|Aktarımını yönetir [CString](../../atl-mfc-shared/reference/cstringt-class.md) bir liste kutusu denetimi ve bir kayıt kümesi alan veri üyeleri arasında veri. Bu işlev öğesi veri denetime kayıt kümesinden taşırken, belirtilen dizenin karakter ile başlayan liste kutusunda seçer.|  
|[DDX_FieldLBStringExact](#ddx_fieldlbstringexact)|Aktarımını yönetir `CString` bir liste kutusu denetimi ve bir kayıt kümesi alan veri üyeleri arasında veri. Bu işlev, veri denetime kayıt kümesinden taşırken, belirtilen dizeyi tam olarak eşleşen ilk öğe seçer.|  
|[DDX_FieldRadio](#ddx_fieldradio)|Kayıt kümesi alan veri üyesi ve bir grup radyo düğmeleri arasında tamsayı veri aktarımı yapan bir `CRecordView` veya `CDaoRecordView`.|  
|[DDX_FieldScroll](#ddx_fieldscroll)|Bir kaydırma çubuğu denetiminde kaydırma konumunu alır veya ayarlar bir `CRecordView` veya `CDaoRecordView`. Çağırmanıza, [DoFieldExchange](../../mfc/reference/cdaorecordset-class.md#dofieldexchange) işlevi.|  
|[DDX_FieldSlider](#ddx_fieldslider)|Kayıt görünümü kaydırıcı denetimi kaydırma konumunu eşitler ve bir `int` kümesinin alan veri üyesi. |
|[DDX_FieldText](#ddx_fieldtext)|Aşırı yüklenmiş sürümleri aktarmak için `int`, **UINT**, **uzun**, `DWORD`, [CString](../../atl-mfc-shared/reference/cstringt-class.md), **float** , **çift**, **kısa**, [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md), ve [COleCurrency](../../mfc/reference/colecurrency-class.md) kayıt kümesi alan veri üyesi ve bir düzen arasında veri kutusunda bir `CRecordView` veya `CDaoRecordView`.|  
  
##  <a name="ddx_fieldcbindex"></a>Ddx_fieldcbındex  
 `DDX_FieldCBIndex` İşlevi kayıt görünümü birleşik giriş kutusu denetiminde liste kutusu denetimini içinde seçilen öğenin dizinini eşitler ve bir `int` kayıt görünümü ile ilişkili bir kayıt kümesinin alan veri üyesi.  
  
```  
void AFXAPI DDX_FieldCBIndex(
    CDataExchange* pDX,    
    int nIDC,   
    int& index,  
    CRecordset* pRecordset);

void AFXAPI DDX_FieldCBIndex(
    CDataExchange* pDX,    
    int nIDC,   
    int& index,  
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 `nIDC`  
 Bir denetimin kimliği [CRecordView](../../mfc/reference/crecordview-class.md) veya [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) nesnesi.  
  
 *Dizin*  
 Alan veri üyesi ilişkili başvuru `CRecordset` veya `CDaoRecordset` nesnesi.  
  
 `pRecordset`  
 Bir işaretçi [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) ile veri değişimi nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Veri denetime kayıt kümesinden taşırken, bu işlev belirtilen değere göre denetimindeki seçim ayarlar *dizin*. Kayıt kümesi alanı Null ise bir transfer üzerinde kayıt kümesinden denetlemek için MFC dizin değerini 0 olarak ayarlar. Bir aktarımı üzerinde denetim kayıt kümesi için Denetim boş ise veya öğe seçili değilse, kayıt kümesi alanı 0 olarak ayarlanır.  
  
 ODBC tabanlı sınıflarıyla çalışıyorsanız ilk sürümü kullanın. DAO tabanlı sınıflar ile çalışıyorsanız, ikinci sürümü kullanın.  
  
 DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md). Örnekler ve için DDX hakkında daha fazla bilgi için [CRecordView](../../mfc/reference/crecordview-class.md) ve [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) alanları başlıklı makaleye bakın [kayıt görünümleri](../../data/record-views-mfc-data-access.md).  
  
### <a name="example"></a>Örnek  
 Bkz: [DDX_FieldText](#ddx_fieldtext) genel DDX_Field örneğin. Bu örnek için benzer `DDX_FieldCBIndex`.  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdao.h  

##  <a name="ddx_fieldcbstring"></a>DDX_FieldCBString  
 `DDX_FieldCBString` İşlevi aktarımını yönetir [CString](../../atl-mfc-shared/reference/cstringt-class.md) kayıt görünümü birleşik giriş kutusu denetiminde düzenleme denetimi arasında veri ve `CString` kayıt görünümü ile ilişkili bir kayıt kümesinin alan veri üyesi.  
  
```  
void AFXAPI DDX_FieldCBString(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldCBString(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 `nIDC`  
 Bir denetimin kimliği [CRecordView](../../mfc/reference/crecordview-class.md) veya [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) nesnesi.  
  
 *value*  
 Alan veri üyesi ilişkili başvuru `CRecordset` veya `CDaoRecordset` nesnesi.  
  
 `pRecordset`  
 Bir işaretçi [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) ile veri değişimi nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Veri denetime kayıt kümesinden taşırken, bu işlev geçerli seçim karakter içinde belirtilen dize ile başlayan ilk satırın açılan kutu ayarlar *değeri*. Bir kayıt kümesi aktarımı denetlemek için kayıt kümesi alan Null ise, açılan kutudan herhangi bir seçimi kaldırılır ve birleşik giriş kutusu düzen denetimi ayarlayın boş. Denetimi boşsa, alanın izin veriyorsa bir aktarımı üzerinde denetiminden kayıt kümesine kayıt kümesi alanı Null olarak ayarlanır.  
  
 ODBC tabanlı sınıflarıyla çalışıyorsanız ilk sürümü kullanın. DAO tabanlı sınıflar ile çalışıyorsanız, ikinci sürümü kullanın.  
  
 DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md). Örnekler ve için DDX hakkında daha fazla bilgi için [CRecordView](../../mfc/reference/crecordview-class.md) ve [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) alanları başlıklı makaleye bakın [kayıt görünümleri](../../data/record-views-mfc-data-access.md).  
  
### <a name="example"></a>Örnek  
 Bkz: [DDX_FieldText](#ddx_fieldtext) genel DDX_Field örneğin. Örnek bir çağrı içerir `DDX_FieldCBString`.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdao.h  
  
## <a name="ddx_fieldcbstringexact"></a>DDX_FieldCBStringExact  
 `DDX_FieldCBStringExact` İşlevi aktarımını yönetir [CString](../../atl-mfc-shared/reference/cstringt-class.md) kayıt görünümü birleşik giriş kutusu denetiminde düzenleme denetimi arasında veri ve `CString` kayıt görünümü ile ilişkili bir kayıt kümesinin alan veri üyesi.  
  
```  
void AFXAPI DDX_FieldCBStringExact(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldCBStringExact(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 `nIDC`  
 Bir denetimin kimliği [CRecordView](../../mfc/reference/crecordview-class.md) veya [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) nesnesi.  
  
 *value*  
 Alan veri üyesi ilişkili başvuru `CRecordset` veya `CDaoRecordset` nesnesi.  
  
 `pRecordset`  
 Bir işaretçi [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) ile veri değişimi nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Veri denetime kayıt kümesinden taşırken, bu işlev geçerli seçim içinde belirtilen dize tam olarak eşleşen ilk satır birleşik giriş kutusu ayarlar *değeri*. Bir kayıt kümesi aktarımı denetlemek için kayıt kümesi alan NULL ise, açılan kutudan herhangi bir seçimi kaldırılır ve birleşik giriş kutusu düzenleme kutusuna ayarlayın boş. Denetim boşsa, bir aktarımı üzerinde denetiminden kayıt kümesine kayıt kümesi alanı NULL olarak ayarlanır.  
  
 ODBC tabanlı sınıflarıyla çalışıyorsanız ilk sürümü kullanın. DAO tabanlı sınıflar ile çalışıyorsanız, ikinci sürümü kullanın.  
  
 DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md). Örnekler ve için DDX hakkında daha fazla bilgi için [CRecordView](../../mfc/reference/crecordview-class.md) ve [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) alanları başlıklı makaleye bakın [kayıt görünümleri](../../data/record-views-mfc-data-access.md).  
  
### <a name="example"></a>Örnek  
 Bkz: [DDX_FieldText](#ddx_fieldtext) genel DDX_Field örneğin. Çağrılar `DDX_FieldCBStringExact` benzer olacaktır.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdao.h  
  
##  <a name="ddx_fieldcheck"></a>DDX_FieldCheck  
 `DDX_FieldCheck` İşlevi aktarımını yönetir `int` iletişim kutusunda, onay kutusu denetimi arasında veri form görünümü ya da Denetim Görünüm nesnesi ve bir `int` veri üyesi iletişim kutusu, form görünümü ya da Denetim Görünüm nesnesi.  
  
```  
void AFXAPI DDX_FieldCheck(
    CDataExchange* pDX,    
    int nIDC,   
    int& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldCheck(
    CDataExchange* pDX,    
    int nIDC,   
    int& value,   
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 `nIDC`  
 Denetim özellik ile ilişkilendirilmiş onay kutusu denetimi kaynak kimliği.  
  
 *value*  
 İletişim kutusu, form görünümü veya denetim görünüm nesnesi ile veri değişimi üye değişkeni bir başvuru.  
  
 `pRecordset`  
 Bir işaretçi [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) ile veri değişimi nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Zaman `DDX_FieldCheck` olarak adlandırılır, *değeri* onay kutusu denetimi geçerli durumuna ayarlanır veya denetimin durumunu ayarlamak *değeri*aktarımı yönünü bağlı olarak.  
  
 DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdao.h  
  
##  <a name="ddx_fieldlbindex"></a>Ddx_fieldlbındex  
 `DDX_FieldLBIndex` İşlevi bir liste kutusu denetimini kayıt görünümünde seçilen öğeyi dizinini eşitler ve bir `int` kayıt görünümü ile ilişkili bir kayıt kümesinin alan veri üyesi.  
  
```  
void AFXAPI DDX_FieldLBIndex(
    CDataExchange* pDX,    
    int nIDC,   
    int& index,  
    CRecordset* pRecordset);

void AFXAPI DDX_FieldLBIndex(
    CDataExchange* pDX,    
    int nIDC,   
    int& index,  
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 `nIDC`  
 Bir denetimin kimliği [CRecordView](../../mfc/reference/crecordview-class.md) veya [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) nesnesi.  
  
 *Dizin*  
 Alan veri üyesi ilişkili başvuru `CRecordset` veya `CDaoRecordset` nesnesi.  
  
 `pRecordset`  
 Bir işaretçi [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) ile veri değişimi nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Veri denetime kayıt kümesinden taşırken, bu işlev belirtilen değere göre denetimindeki seçim ayarlar *dizin*. Kayıt kümesi alanı Null ise bir transfer üzerinde kayıt kümesinden denetlemek için MFC dizin değerini 0 olarak ayarlar. Denetimi boşsa, bir aktarımı üzerinde denetiminden kayıt kümesine kayıt kümesi alanı 0 olarak ayarlanır.  
  
 ODBC tabanlı sınıflarıyla çalışıyorsanız ilk sürümü kullanın. DAO tabanlı sınıflar ile çalışıyorsanız, ikinci sürümü kullanın.  
  
 DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md). Örnekler ve için DDX hakkında daha fazla bilgi için [CRecordView](../../mfc/reference/crecordview-class.md) ve [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) alanları başlıklı makaleye bakın [kayıt görünümleri](../../data/record-views-mfc-data-access.md).  
  
### <a name="example"></a>Örnek  
 Bkz: [DDX_FieldText](#ddx_fieldtext) genel DDX_Field örneğin.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdao.h  
  
##  <a name="ddx_fieldlbstring"></a>DDX_FieldLBString  
 `DDX_FieldLBString` Liste kutusu denetimi, geçerli seçim için kayıt görünümünde kopyalar bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) kayıt görünümü ile ilişkili bir kayıt kümesinin alan veri üyesi.  
  
```  
void AFXAPI DDX_FieldLBString(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldLBString(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 `nIDC`  
 Bir denetimin kimliği [CRecordView](../../mfc/reference/crecordview-class.md) veya [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) nesnesi.  
  
 *value*  
 Alan veri üyesi ilişkili başvuru `CRecordset` veya `CDaoRecordset` nesnesi.  
  
 `pRecordset`  
 Bir işaretçi [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) ile veri değişimi nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Ters yönde, bu işlev tarafından belirtilen dizedeki karakter ile başlayan ilk satırına liste kutusunda geçerli seçim ayarlar *değeri*. Kayıt kümesi alanı Null ise bir aktarımı üzerinde kayıt denetlemek için liste kutusundan herhangi bir seçimi kaldırılır. Denetim boşsa, bir aktarımı üzerinde denetiminden kayıt kümesine kayıt kümesi alanı Null olarak ayarlanır.  
  
 ODBC tabanlı sınıflarıyla çalışıyorsanız ilk sürümü kullanın. DAO tabanlı sınıflar ile çalışıyorsanız, ikinci sürümü kullanın.  
  
 DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md). Örnekler ve için DDX hakkında daha fazla bilgi için [CRecordView](../../mfc/reference/crecordview-class.md) ve [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) alanları başlıklı makaleye bakın [kayıt görünümleri](../../data/record-views-mfc-data-access.md).  
  
### <a name="example"></a>Örnek  
 Bkz: [DDX_FieldText](#ddx_fieldtext) genel DDX_Field örneğin. Çağrılar `DDX_FieldLBString` benzer olacaktır.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdao.h  
  
##  <a name="ddx_fieldlbstringexact"></a>DDX_FieldLBStringExact  
 `DDX_FieldLBStringExact` İşlevi için bir kayıt görünümünde bir liste kutusu denetimini geçerli seçimi kopyalar bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) kayıt görünümü ile ilişkili bir kayıt kümesinin alan veri üyesi.  
  
```  
void AFXAPI DDX_FieldLBStringExact(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldLBStringExact(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 `nIDC`  
 Bir denetimin kimliği [CRecordView](../../mfc/reference/crecordview-class.md) veya [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) nesnesi.  
  
 *value*  
 Alan veri üyesi ilişkili başvuru `CRecordset` veya `CDaoRecordset` nesnesi.  
  
 `pRecordset`  
 Bir işaretçi [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) ile veri değişimi nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Ters yönde, bu işlev içinde belirtilen dize tam olarak eşleşen ilk satır liste kutusunda geçerli seçim ayarlar *değeri*. Kayıt kümesi alanı Null ise bir aktarımı üzerinde kayıt denetlemek için liste kutusundan herhangi bir seçimi kaldırılır. Denetim boşsa, bir aktarımı üzerinde denetiminden kayıt kümesine kayıt kümesi alanı Null olarak ayarlanır.  
  
 ODBC tabanlı sınıflarıyla çalışıyorsanız ilk sürümü kullanın. DAO tabanlı sınıflar ile çalışıyorsanız, ikinci sürümü kullanın.  
  
 DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md). Örnekler ve için DDX hakkında daha fazla bilgi için [CRecordView](../../mfc/reference/crecordview-class.md) ve [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) alanları başlıklı makaleye bakın [kayıt görünümleri](../../data/record-views-mfc-data-access.md).  
  
### <a name="example"></a>Örnek  
 Bkz: [DDX_FieldText](#ddx_fieldtext) genel DDX_Field örneğin. Çağrılar `DDX_FieldLBStringExact` benzer olacaktır.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdao.h  
  
##  <a name="ddx_fieldradio"></a>DDX_FieldRadio  
 `DDX_FieldRadio` İşlevi sıfır tabanlı bir ilişkilendirir `int` üye değişkeni şu anda seçili radyo düğmesi grubundaki kayıt görünümü radyo düğmeleri ile kayıt görünümünün kümesi.  
  
```  
void AFXAPI DDX_FieldRadio(
    CDataExchange* pDX,    
    int nIDC,   
    int& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldRadio(
    CDataExchange* pDX,    
    int nIDC,   
    int& value,   
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 `nIDC`  
 İlk Kimliğini gruptaki (stiliyle **WS_GROUP**) bitişik radyo düğmesi denetimlerin [CRecordView](../../mfc/reference/crecordview-class.md) veya [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) nesnesi.  
  
 *value*  
 Alan veri üyesi ilişkili başvuru `CRecordset` veya `CDaoRecordset` nesnesi.  
  
 `pRecordset`  
 Bir işaretçi [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) ile veri değişimi nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Kayıt kümesi alanından görünüme aktarılırken bu işlevi etkinleştirir *n.* radyo düğmesi (sıfır tabanlı) ve diğer düğmeleri devre dışı bırakır. Ters yönde bu işlev, kayıt kümesi alanı şu anda (checked üzerinde) radyo düğmesi sıra sayısını ayarlar. Kayıt kümesi alanı Null ise bir aktarımı üzerinde kayıt denetlemek için hiçbir düğmesi seçilir. Hiçbir denetim seçili ise, alan izin veriliyorsa bir aktarımı üzerinde denetiminden kayıt kümesine kayıt kümesi alanı Null olarak ayarlanır.  
  
 ODBC tabanlı sınıflarıyla çalışıyorsanız ilk sürümü kullanın. DAO tabanlı sınıflar ile çalışıyorsanız, ikinci sürümü kullanın.  
  
 DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md). Örnekler ve için DDX hakkında daha fazla bilgi için [CRecordView](../../mfc/reference/crecordview-class.md) ve [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) alanları başlıklı makaleye bakın [kayıt görünümleri](../../data/record-views-mfc-data-access.md).  
  
### <a name="example"></a>Örnek  
 Bkz: [DDX_FieldText](#ddx_fieldtext) genel DDX_Field örneğin. Çağrılar `DDX_FieldRadio` benzer olacaktır.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdao.h  
  
##  <a name="ddx_fieldscroll"></a>DDX_FieldScroll  
 `DDX_FieldScroll` İşlevi kayıt görünümü kaydırma çubuğu denetimi kaydırma konumunu eşitler ve bir `int` kayıt görünümü ile (veya seçtiğiniz için eşlemek için hangi tamsayı değişken) ilişkili bir kayıt kümesinin alan veri üyesi.  
  
```  
void AFXAPI DDX_FieldScroll(
    CDataExchange* pDX,    
    int nIDC,   
    int& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldScroll(
    CDataExchange* pDX,    
    int nIDC,   
    int& value,   
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 *nIDC\**  
 İlk Kimliğini gruptaki (stiliyle **WS_GROUP**) bitişik radyo düğmesi denetimlerin [CRecordView](../../mfc/reference/crecordview-class.md) veya [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) nesnesi.  
  
 *value*  
 Alan veri üyesi ilişkili başvuru `CRecordset` veya `CDaoRecordset` nesnesi.  
  
 `pRecordset`  
 Bir işaretçi [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) ile veri değişimi nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev kaydırma çubuğu denetimi kaydırma konumunu veri denetime kayıt kümesinden taşırken, belirtilen değere ayarlar. *değeri*. Kayıt kümesi alanı Null ise bir aktarımı üzerinde kayıt denetlemek için kaydırma çubuğu denetimi 0 olarak ayarlanır. Denetim boşsa, bir aktarımı üzerinde denetiminden kayıt kümesine kayıt kümesi alanının değeri 0'dır.  
  
 ODBC tabanlı sınıflarıyla çalışıyorsanız ilk sürümü kullanın. DAO tabanlı sınıflar ile çalışıyorsanız, ikinci sürümü kullanın.  
  
 DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md). Örnekler ve için DDX hakkında daha fazla bilgi için [CRecordView](../../mfc/reference/crecordview-class.md) ve [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) alanları başlıklı makaleye bakın [kayıt görünümleri](../../data/record-views-mfc-data-access.md).  
  
### <a name="example"></a>Örnek  
 Bkz: [DDX_FieldText](#ddx_fieldtext) genel DDX_Field örneğin. Çağrılar `DDX_FieldScroll` benzer olacaktır.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdao.h  

  ## <a name="nameddxfieldslidera--ddxfieldslider"></a>adı "ddx_fieldslider" = ></a> DDX_FieldSlider
`DDX_FieldSlider` İşlevi kayıt görünümü kaydırıcı denetimi kaydırma konumunu eşitler ve bir `int` kayıt görünümü ile (veya seçtiğiniz için eşlemek için hangi tamsayı değişken) ilişkili bir kayıt kümesinin alan veri üyesi.  
   
### <a name="syntax"></a>Sözdizimi  
  ```
   void AFXAPI DDX_FieldSlider(  
       CDataExchange* pDX,  
       int nIDC,  
       int& value,  
       CRecordset* pRecordset );  

void AFXAPI DDX_FieldSlider(  
     CDataExchange* pDX,  
     int nIDC,  
     int& value,  
     CDaoRecordset* pRecordset );  
```
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir [CDataExchange](cdataexchange-class.md) nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 `nIDC`  
 Kaydırıcı denetimi kaynak kimliği.  
  
 *value*  
 Değiştirilebilmesi için değeri referansı. Bu parametre tutan veya kaydırıcı denetimin geçerli kaydırma konumunu ayarlamak için kullanılır.  
  
 `pRecordset`  
 İlişkili bir işaretçi `CRecordset` veya `CDaoRecordset` ile veri değişimi nesnesi.  
   
### <a name="remarks"></a>Açıklamalar  
 Veri kaydırıcıyı kayıt kümesinden taşırken, bu işlev için belirtilen değer kaydırıcıyı konumunu ayarlar *değeri*. Kayıt kümesi alanı Null ise bir aktarımı üzerinde kayıt denetlemek için kaydırıcıyı denetimin konumu 0 olarak ayarlanır. Denetim boşsa, bir aktarımı üzerinde denetiminden kayıt kümesine kayıt kümesi alanının değeri 0'dır.  
  
 `DDX_FieldSlider`Kaydırıcı denetimleri yalnızca bir konum yerine bir aralığı ayarını özellikli aralığı bilgilerle exchange değil.  
  
 ODBC tabanlı sınıflarıyla çalışıyorsanız işlevi ilk geçersiz kılma kullanın. İkinci geçersiz kılma DAO tabanlı sınıflarıyla kullanın.  
  
 DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../dialog-data-exchange-and-validation.md). Örnekler ve için DDX hakkında daha fazla bilgi için `CRecordView` ve `CDaoRecordView` alanları görmek [kayıt görünümleri](../../data/record-views-mfc-data-access.md). Kaydırıcı denetimleri hakkında daha fazla bilgi için bkz: [kullanarak CSliderCtrl](../using-csliderctrl.md).  
   
### <a name="example"></a>Örnek  
 Bkz: [DDX_FieldText](#ddx_fieldtext) genel DDX_Field örneğin. Çağrılar `DDX_FieldSlider` benzer olacaktır.  
   
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdao.h  
   
### <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](mfc-macros-and-globals.md)   
  
##  <a name="ddx_fieldtext"></a>DDX_FieldText  
 `DDX_FieldText` İşlevi aktarımını yönetir `int`, **kısa**, **uzun**, `DWORD`, [CString](../../atl-mfc-shared/reference/cstringt-class.md), **float**, **çift**, **BOOL**, veya **bayt** düzenleme kutusu denetimine ve bir kayıt kümesi alan veri üyeleri arasında veri.  
  
```  
void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    BYTE& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    int& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    UINT& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    long& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    DWORD& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    float& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    double& value,   
    CRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    short& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    BOOL& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    BYTE& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    long& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    DWORD& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    CString& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    float& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    double& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    COleDateTime& value,   
    CDaoRecordset* pRecordset);

void AFXAPI DDX_FieldText(
    CDataExchange* pDX,    
    int nIDC,   
    COleCurrency& value,   
    CDaoRecordset* pRecordset);  
```  
  
### <a name="parameters"></a>Parametreler  
 `pDX`  
 Bir işaretçi bir [CDataExchange](../../mfc/reference/cdataexchange-class.md) nesnesi. Framework yön dahil olmak üzere veri değişimi içeriği oluşturmak için bu nesneyi sağlar.  
  
 `nIDC`  
 Bir denetimin kimliği [CRecordView](../../mfc/reference/crecordview-class.md) veya [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) nesnesi.  
  
 *value*  
 Alan veri üyesi ilişkili başvuru `CRecordset` veya `CDaoRecordset` nesnesi. Değerin veri türü bağımlı olduğu aşırı yüklenmiş sürümlerinin `DDX_FieldText` kullanın.  
  
 `pRecordset`  
 Bir işaretçi [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) ile veri değişimi nesnesi. Bu işaretçinin etkinleştirir `DDX_FieldText` algılamasını ve Null değerleri ayarlayın.  
  
### <a name="remarks"></a>Açıklamalar  
 İçin [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesneleri `DDX_FieldText` da aktarma yönetir [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md), ve [COleCurrency](../../mfc/reference/colecurrency-class.md) değerleri. Boş düzenleme kutusu denetimine Null değeri gösterir. Düzenleme kutusuna üzerindeki bir aktarımı kayıt kümesinden denetlemek için kayıt kümesi alanı Null ise ayarlanmış boş. Denetim boşsa, bir aktarımı üzerinde denetiminden kayıt kümesine kayıt kümesi alanı Null olarak ayarlanır.  
  
 Sürümleriyle kullanmak [CRecordset](../../mfc/reference/crecordset-class.md) ODBC tabanlı sınıflarıyla çalışıyorsanız parametreleri. Sürümleriyle kullanmak [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) DAO tabanlı sınıflarıyla çalışıyorsanız parametreleri.  
  
 DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md). Örnekler ve için DDX hakkında daha fazla bilgi için [CRecordView](../../mfc/reference/crecordview-class.md) ve [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) alanları başlıklı makaleye bakın [kayıt görünümleri](../../data/record-views-mfc-data-access.md).  
  
### <a name="example"></a>Örnek  
 Aşağıdaki `DoDataExchange` için işlev bir [CRecordView](../../mfc/reference/crecordview-class.md) içeren `DDX_FieldText` işlev çağrıları için üç veri türleri: `IDC_COURSELIST` bir birleşik giriş kutusu; diğer iki denetimleri düzenleme kutularıdır. DAO programlama için *m_pSet* parametredir gösteren bir işaretçi bir [CRecordset](../../mfc/reference/crecordset-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).  
  
 [!code-cpp[NVC_MFCDatabase#43](../../mfc/codesnippet/cpp/dialog-data-exchange-functions-for-crecordview-and-cdaorecordview_1.cpp)]  

  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdao.h  
    
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)
