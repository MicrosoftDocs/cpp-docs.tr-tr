---
title: "CDaoFieldExchange sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDaoFieldExchange
- AFXDAO/CDaoFieldExchange
- AFXDAO/CDaoFieldExchange::IsValidOperation
- AFXDAO/CDaoFieldExchange::SetFieldType
- AFXDAO/CDaoFieldExchange::m_nOperation
- AFXDAO/CDaoFieldExchange::m_prs
dev_langs: C++
helpviewer_keywords:
- CDaoFieldExchange [MFC], IsValidOperation
- CDaoFieldExchange [MFC], SetFieldType
- CDaoFieldExchange [MFC], m_nOperation
- CDaoFieldExchange [MFC], m_prs
ms.assetid: 350a663e-92ff-44ab-ad53-d94efa2e5823
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b95af3e80234cf7f3910fc9a4ef3468ab5d90ba7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cdaofieldexchange-class"></a>CDaoFieldExchange sınıfı
DAO veritabanı sınıfları tarafından kullanılan DAO kayıt alanı değişimi (DFX) yordamları destekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CDaoFieldExchange  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDaoFieldExchange::IsValidOperation](#isvalidoperation)|Geçerli işlem ise sıfır olmayan döndürür güncelleştirilmekte alan türü için uygun.|  
|[CDaoFieldExchange::SetFieldType](#setfieldtype)|Kayıt kümesi veri üyesi türünü belirtir — sütunu veya parametresi — tüm sonraki çağrılar DFX işlevleri tarafından temsil edilen sonraki çağrısı kadar `SetFieldType`.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDaoFieldExchange::m_nOperation](#m_noperation)|Kayıt kümesinin geçerli çağrısı tarafından gerçekleştirilen DFX işlemi `DoFieldExchange` üye işlevi.|  
|[CDaoFieldExchange::m_prs](#m_prs)|Hangi DFX üzerinde işlem gerçekleştiriliyor kayıt kümesi için bir işaretçi.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CDaoFieldExchange`bir taban sınıfı yok.  
  
 Özel veri türleri için veri değişimi rutinleri yazıyorsanız, bu sınıfı kullanın; Aksi takdirde, bu sınıfın doğrudan kullanmaz. DFX alan veri üyeleri arasında veri alış verişleri, [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesne ve geçerli kayıt veri kaynağı için karşılık gelen alanları. DFX veri kaynağından ve veri kaynağı için her iki yönde exchange yönetir. Bkz: [Teknik Not 53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md) özel DFX yordamları yazma konusunda bilgi.  
  
> [!NOTE]
>  DAO veritabanı sınıfları açık veritabanı bağlantısı (ODBC) üzerinde tabanlı MFC veritabanı sınıfları farklıdır. Tüm DAO veritabanı sınıf adları "CDao" önekini alır. DAO sınıfları ile erişim ODBC veri kaynakları hala kullanabilirsiniz. Genel olarak, üzerinde DAO tabanlı MFC sınıfları ODBC tabanlı MFC sınıfları'den fazla özelliğine sahiptir. DAO tabanlı sınıflar kendi veritabanı altyapısı aracılığıyla ODBC sürücüleri üzerinden de dahil olmak üzere, verilere erişebilir. Bunlar ayrıca kendiniz çağırmak zorunda kalmak yerine sınıfları aracılığıyla tablolar ekleme gibi veri tanımlama dili (DDL) işlemleri destekler.  
  
> [!NOTE]
>  DAO kayıt alanı değişimi (DFX) benzer çok ODBC tabanlı MFC veritabanı sınıfları içinde kayıt alanı değişimi (RFX) ( `CDatabase`, `CRecordset`). RFX anlarsanız, kullanımı kolay DFX bulacaksınız.  
  
 A `CDaoFieldExchange` nesnesi, bağlam bilgilerini DAO için kayıt alanı değişimi gerçekleşmesi sağlar. `CDaoFieldExchange`nesneleri bir dizi bağlama parametreleri ve alan veri üyeleri de dahil olmak üzere ve geçerli kayıt alanlarını üzerinde çeşitli bayrakları ayarlama işlemi destekler. Kayıt kümesi sınıfı verileri üyeleri tarafından tanımlanan türleri üzerinde gerçekleştirilen DFX işlemler `enum` **FieldType** içinde `CDaoFieldExchange`. Olası **FieldType** değerler şunlardır:  
  
- **CDaoFieldExchange::outputColumn** alan veri üyeleri için.  
  
- **CDaoFieldExchange::param** parametre veri üyeleri için.  
  
 [IsValidOperation](#isvalidoperation) üye işlevi, kendi özel DFX yordamları yazmak için sağlanır. Kullanacağınız [SetFieldType](#setfieldtype) sıklıkla, [CDaoRecordset::DoFieldExchange](../../mfc/reference/cdaorecordset-class.md#dofieldexchange) işlevleri. DFX genel işlevler hakkında daha fazla ayrıntı için bkz: [kayıt alanı değişim işlevleri](../../mfc/reference/record-field-exchange-functions.md). Kendi veri türleri için özel DFX yordamları yazma hakkında daha fazla bilgi için bkz: [Teknik Not 53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CDaoFieldExchange`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdao.h  
  
##  <a name="isvalidoperation"></a>CDaoFieldExchange::IsValidOperation  
 Kendi DFX işlevi yazarsanız, çağrı `IsValidOperation` üzerinde belirli alan veri üye türü geçerli işlemi gerçekleştirip gerçekleştirmediğini belirlemek için işlevinizi başındaki (bir **CDaoFieldExchange::outputColumn** veya **CDaoFieldExchange::param**).  
  
```  
BOOL IsValidOperation();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli işlem güncelleştirilmekte alan türü için uygun olup olmadığını sıfır olmayan.  
  
### <a name="remarks"></a>Açıklamalar  
 DFX mekanizması tarafından gerçekleştirilen işlemler bazıları olası alan türleri yalnızca biri için geçerlidir. Varolan DFX işlevleri modelinin izleyin.  
  
 Özel DFX yordamları yazma hakkında ek bilgi için bkz: [Teknik Not 53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md).  
  
##  <a name="m_noperation"></a>CDaoFieldExchange::m_nOperation  
 Gerçekleştirilecek işlem tanımlayan [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) alan exchange nesneyle ilişkili nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 `CDaoFieldExchange` Nesne kayıt kümesi üzerindeki farklı DFX işlemlerinin sayısı için bağlamı sağlar.  
  
> [!NOTE]
>  **PSEUDONULL** aşağıdaki MarkForAddNew ve SetFieldNull işlemleri altında açıklanan değerin, alanları Null işaretlemek için kullanılan bir değerdir. DAO kayıt alanı değişimi mekanizması (DFX) hangi alanların Null açık olarak işaretlenmiş belirlemek için bu değeri kullanır. **PSEUDONULL** gerekli değildir [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) ve [COleCurrency](../../mfc/reference/colecurrency-class.md) alanları.  
  
 Olası değerlerini **CFieldExchange** şunlardır:  
  
|Çalışma|Açıklama|  
|---------------|-----------------|  
|**AddToParameterList**|Derlemeler **parametreleri** SQL deyiminin yan tümcesi.|  
|**AddToSelectList**|Derlemeler **seçin** SQL deyiminin yan tümcesi.|  
|**BindField**|Veritabanı alanına uygulamanızda bellek konumuna bağlar.|  
|**BindParam**|Kayıt kümesinin sorgu için parametre değerlerini ayarlar.|  
|**Düzeltmesi**|Bir alan için Null durumunu ayarlar.|  
|**AllocCache**|Kayıt kümesi "kirli" alanlarını denetlemek için kullanılan önbellek ayırır.|  
|**StoreField**|Geçerli kayıt önbelleğine kaydeder.|  
|**LoadField**|Önbelleğe alınan veriler üye değişkenleri kümesinde geri yükler.|  
|**FreeCache**|Kayıt kümesi "kirli" alanlarını denetlemek için kullanılan önbelleği boşaltır.|  
|`SetFieldNull`|Bir alanın durumu Null değerine ayarlar **PSEUDONULL**.|  
|**MarkForAddNew**|Aksi durumda alanları "kirli" işaretler **PSEUDONULL**.|  
|**MarkForEdit**|Önbellek eşleşmiyorsa alanları "kirli" olarak işaretler.|  
|**SetDirtyField**|Ayarlar "kirli" olarak işaretlenmiş değerleri alan|  
|**DumpField**|Bir alanın içeriği (yalnızca hata ayıklama) dökümünü alır.|  
|**MaxDFXOperation**|Giriş denetlemek için kullanılır.|  
  
##  <a name="m_prs"></a>CDaoFieldExchange::m_prs  
 Bir işaretçi içeriyor [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) ilişkili nesne `CDaoFieldExchange` nesne.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setfieldtype"></a>CDaoFieldExchange::SetFieldType  
 Çağrı `SetFieldType` içinde `CDaoRecordset` sınıfının `DoFieldExchange` geçersiz kılar.  
  
```  
void SetFieldType(UINT nFieldType);
```  
  
### <a name="parameters"></a>Parametreler  
 `nFieldType`  
 Değerini **enum FieldType**bildirilen `CDaoFieldExchange`, olabilen aşağıdakilerden birini:  
  
- **CDaoFieldExchange::outputColumn**  
  
- **CDaoFieldExchange::param**  
  
### <a name="remarks"></a>Açıklamalar  
 Normal şekilde ClassWizard bu çağrı, yazar. Kendi işlevi yazma ve yazmak için Sihirbazı'nı kullanarak, `DoFieldExchange` işlev, alan haritası dışında kendi işlev çağrıları ekleyin. Sihirbaz kullanmazsanız, alan eşleştirme olmayacak. Arama, sınıfın her alan veri üyesi için bir tane DFX işlevleri çağrıları önündeki ve alan türü olarak tanımlayan **CDaoFieldExchange::outputColumn**.  
  
 Kayıt kümesi sınıfınız Parametreleştirme varsa (alan eşleme dışında) tüm parametre veri üyeleri için DFX çağrıları eklemeli ve bu çağrıları çağrısıyla önünde `SetFieldType`. Değer geçirmek **CDaoFieldExchange::param**. (Bunun yerine, kullanabilirsiniz bir [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) ve parametre değerlerini ayarlar.)  
  
 DFX işlev çağrılarını alan veri üyeleri veya parametre veri üyeleri ile ilişkili her grup için bir çağrı tarafından genel olarak, gelmelidir `SetFieldType`. `nFieldType` Her parametre `SetFieldType` çağrısı izleyin DFX işlev çağrıları tarafından temsil edilen veri üyeleri türünü tanımlayan `SetFieldType` çağırın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CDaoRecordset sınıfı](../../mfc/reference/cdaorecordset-class.md)
