---
title: Makrolar ve genel işlevler için OLE DB Tüketici Şablonları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- vc.templates.ole
- ATL.AtlTraceErrorRecords
- ATL::AtlTraceErrorRecords
- AtlTraceErrorRecords
- BEGIN_ACCESSOR
- BEGIN_ACCESSOR_MAP
- END_ACCESSOR
- END_ACCESSOR_MAP
- BEGIN_COLUMN_MAP
- BLOB_ENTRY
- BLOB_ENTRY_LENGTH
- BLOB_ENTRY_LENGTH_STATUS
- BLOB_ENTRY_STATUS
- BLOB_NAME
- BLOB_NAME_LENGTH
- BLOB_NAME_LENGTH_STATUS
- BLOB_NAME_STATUS
- BOOKMARK_ENTRY
- COLUMN_ENTRY
- COLUMN_ENTRY_EX
- COLUMN_ENTRY_LENGTH
- COLUMN_ENTRY_LENGTH_STATUS
- COLUMN_ENTRY_PS
- COLUMN_ENTRY_PS_LENGTH
- COLUMN_ENTRY_PS_LENGTH_STATUS
- COLUMN_ENTRY_PS_STATUS
- COLUMN_ENTRY_STATUS
- COLUMN_ENTRY_TYPE
- COLUMN_ENTRY_TYPE_SIZE
- COLUMN_NAME
- COLUMN_NAME_EX
- COLUMN_NAME_LENGTH
- COLUMN_NAME_LENGTH_STATUS
- COLUMN_NAME_PS
- COLUMN_NAME_PS_LENGTH
- COLUMN_NAME_PS_LENGTH_STATUS
- COLUMN_NAME_PS_STATUS
- COLUMN_NAME_STATUS
- COLUMN_NAME_TYPE
- COLUMN_NAME_TYPE_PS
- COLUMN_NAME_TYPE_SIZE
- COLUMN_NAME_TYPE_STATUS
- END_COLUMN_MAP
- DEFINE_COMMAND
- DEFINE_COMMAND_EX
- BEGIN_PARAM_MAP
- END_PARAM_MAP
- SET_PARAM_TYPE
dev_langs:
- C++
helpviewer_keywords:
- OLE DB consumer templates, macros
- macros, OLE DB consumer template
- AtlTraceErrorRecords function
- BEGIN_ACCESSOR macro, syntax
- BEGIN_ACCESSOR macro
- BEGIN_ACCESSOR_MAP macro
- END_ACCESSOR macro
- END_ACCESSOR_MAP macro
- BEGIN_COLUMN_MAP macro
- BLOB_ENTRY macro
- BLOB_ENTRY_LENGTH macro
- BLOB_ENTRY_LENGTH_STATUS macro
- BLOB_ENTRY_STATUS macro
- BLOB_NAME macro
- BLOB_NAME_LENGTH macro
- BLOB_NAME_LENGTH_STATUS macro
- BLOB_NAME_STATUS macro
- BOOKMARK_ENTRY macro
- COLUMN_ENTRY macro
- COLUMN_ENTRY_EX macro
- COLUMN_ENTRY_LENGTH macro
- COLUMN_ENTRY_LENGTH_STATUS macro
- COLUMN_ENTRY_PS macro
- COLUMN_ENTRY_PS_LENGTH macro
- COLUMN_ENTRY_PS_LENGTH_STATUS macro
- COLUMN_ENTRY_PS_STATUS macro
- COLUMN_ENTRY_STATUS macro
- COLUMN_ENTRY_TYPE macro
- COLUMN_ENTRY_TYPE_SIZE macro
- COLUMN_NAME macro
- COLUMN_NAME_EX macro
- COLUMN_NAME_LENGTH macro
- COLUMN_NAME_LENGTH_STATUS macro
- COLUMN_NAME_PS macro
- COLUMN_NAME_PS_LENGTH macro
- COLUMN_NAME_PS_LENGTH_STATUS macro
- COLUMN_NAME_PS_STATUS macro
- COLUMN_NAME_STATUS macro
- COLUMN_NAME_TYPE macro
- COLUMN_NAME_TYPE_PS macro
- COLUMN_NAME_TYPE_SIZE macro
- COLUMN_NAME_TYPE_STATUS macro
- END_COLUMN_MAP macro
- DEFINE_COMMAND macro
- DEFINE_COMMAND_EX macro
- BEGIN_PARAM_MAP macro
- END_PARAM_MAP macro
- SET_PARAM_TYPE macro
ms.assetid: 8765eb7b-32dd-407c-bacf-8890ef959837
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a915a581a574193918f86f80083d3202c9949674
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39338154"
---
# <a name="macros-and-global-functions-for-ole-db-consumer-templates"></a>OLE DB Tüketici Şablonları için Makrolar ve Genel İşlevler
OLE DB Tüketici şablonları aşağıdaki makroları ve genel işlevler şunlardır:  
  
## <a name="global-functions"></a>Genel işlevleri  
  
|||  
|-|-|  
|[AtlTraceErrorRecords](#atltraceerrorrecords)|Bir hata döndürülürse, OLE DB hata kaydı bilgi döküm cihaza dökümünü yapar.|  
  
## <a name="accessor-map-macros"></a>Erişimci eşleme makroları  
  
|||  
|-|-|  
|[BEGIN_ACCESSOR](#begin_accessor)|Bir erişimci giriş başlangıcına işaret eder.|  
|[BEGIN_ACCESSOR_MAP](#begin_accessor_map)|Erişimci eşleme girişleri başlangıcını işaretler.|  
|[END_ACCESSOR](#end_accessor)|Bir erişimci girdinin sonunu işaretler.|  
|[END_ACCESSOR_MAP](#end_accessor_map)|Erişimci eşleme girişleri sonunu işaretler.|  
  
## <a name="column-map-macros"></a>Sütun eşleme makroları  
  
|||  
|-|-|  
|[BEGIN_COLUMN_MAP](#begin_column_map)|Kullanıcı kayıt sınıfı sütun eşleme girişleri başlangıcını işaretler.|  
|[BLOB_ENTRY](#blob_entry)|İkili büyük nesne (BLOB) bağlamak için kullanılır.|  
|[BLOB_ENTRY_LENGTH](#blob_entry_length)|BLOB veri sütununun uzunluğu bildirir.|  
|[BLOB_ENTRY_LENGTH_STATUS](#blob_entry_length_status)|Uzunluğu ve BLOB veri sütununu durumunu raporlar.|  
|[BLOB_ENTRY_STATUS](#blob_entry_status)|BLOB veri sütununu durumunu raporlar.|  
|[BLOB_NAME](#blob_name)|İkili büyük nesne sütunu adıyla bağlamak için kullanılır.|  
|[BLOB_NAME_LENGTH](#blob_name_length)|BLOB veri sütununun uzunluğu bildirir.|  
|[BLOB_NAME_LENGTH_STATUS](#blob_name_length_status)|Uzunluğu ve BLOB veri sütununu durumunu raporlar.|  
|[BLOB_NAME_STATUS](#blob_name_status)|BLOB veri sütununu durumunu raporlar.|  
|[BOOKMARK_ENTRY](#bookmark_entry)|Satır kümesi bir yer işareti girdisini temsil eder. Bir yer işareti girişi sütunu giriş özel türüdür.|  
|[COLUMN_ENTRY](#column_entry)|Veritabanındaki belirli bir sütuna bağlama temsil eder.|  
|[COLUMN_ENTRY_EX](#column_entry_ex)|Veritabanındaki belirli bir sütuna bağlama temsil eder. Destekler *türü*, *uzunluğu*, *duyarlık*, *ölçek*, ve *durumu* parametreleri.|  
|[COLUMN_ENTRY_LENGTH](#column_entry_length)|Veritabanındaki belirli bir sütuna bağlama temsil eder. Destekler *uzunluğu* değişkeni.|  
|[COLUMN_ENTRY_LENGTH_STATUS](#column_entry_length_status)|Veritabanındaki belirli bir sütuna bağlama temsil eder. Destekler *durumu* ve *uzunluğu* parametreleri.|  
|[COLUMN_ENTRY_PS](#column_entry_ps)|Veritabanındaki belirli bir sütuna bağlama temsil eder. Destekler *duyarlık* ve *ölçek* parametreleri.|  
|[COLUMN_ENTRY_PS_LENGTH](#column_entry_ps_length)|Veritabanındaki belirli bir sütuna bağlama temsil eder. Destekler *uzunluğu* değişken *duyarlık* ve *ölçek* parametreleri.|  
|[COLUMN_ENTRY_PS_LENGTH_STATUS](#column_entry_ps_length_status)|Veritabanındaki belirli bir sütuna bağlama temsil eder. Destekler *durumu* ve *uzunluğu* değişkenleri *duyarlık* ve *ölçek* parametreleri.|  
|[COLUMN_ENTRY_PS_STATUS](#column_entry_ps_status)|Veritabanındaki belirli bir sütuna bağlama temsil eder. Destekler *durumu* değişken *duyarlık* ve *ölçek* parametreleri.|  
|[COLUMN_ENTRY_STATUS](#column_entry_status)|Veritabanındaki belirli bir sütuna bağlama temsil eder. Destekler *durumu* değişkeni.|  
|[COLUMN_ENTRY_TYPE](#column_entry_type)|Veritabanındaki belirli bir sütuna bağlama temsil eder. Destekler *türü* parametresi.|  
|[COLUMN_ENTRY_TYPE_SIZE](#column_entry_type_size)|Veritabanındaki belirli bir sütuna bağlama temsil eder. Destekler *türü* ve *boyutu* parametreleri.|  
|[COLUMN_NAME](#column_name)|Veritabanındaki belirli bir sütuna bağlama adına göre temsil eder.|  
|[COLUMN_NAME_EX](#column_name_ex)|Veritabanındaki belirli bir sütuna bağlama adına göre temsil eder. Veri türü, boyutu, kesinlik, Ölçek, sütun uzunluğu ve sütun durum belirtimini destekler.|  
|[COLUMN_NAME_LENGTH](#column_name_length)|Veritabanındaki belirli bir sütuna bağlama adına göre temsil eder. Sütun uzunluğu belirtimi destekler.|  
|[COLUMN_NAME_LENGTH_STATUS](#column_name_length_status)|Veritabanındaki belirli bir sütuna bağlama adına göre temsil eder. Sütun uzunluğu ve durum belirtimini destekler.|  
|[COLUMN_NAME_PS](#column_name_ps)|Veritabanındaki belirli bir sütuna bağlama adına göre temsil eder. Kesinlik ve ölçek belirtimini destekler.|  
|[COLUMN_NAME_PS_LENGTH](#column_name_ps_length)|Veritabanındaki belirli bir sütuna bağlama adına göre temsil eder. Kesinlik ve ölçek sütun uzunluğu belirtimi destekler.|  
|[COLUMN_NAME_PS_LENGTH_STATUS](#column_name_ps_length_status)|Veritabanındaki belirli bir sütuna bağlama adına göre temsil eder. Duyarlık, Ölçek, sütun uzunluğu ve sütun durum belirtimini destekler.|  
|[COLUMN_NAME_PS_STATUS](#column_name_ps_status)|Veritabanındaki belirli bir sütuna bağlama adına göre temsil eder. Kesinlik ve ölçek sütun durum belirtimini destekler.|  
|[COLUMN_NAME_STATUS](#column_name_status)|Veritabanındaki belirli bir sütuna bağlama adına göre temsil eder. Sütun durumu belirtimini destekler.|  
|[COLUMN_NAME_TYPE](#column_name_type)|Veritabanındaki belirli bir sütuna bağlama adına göre temsil eder. Veri türü belirtimi destekler.|  
|[COLUMN_NAME_TYPE_PS](#column_name_type_ps)|Veritabanındaki belirli bir sütuna bağlama adına göre temsil eder. Veri türü, kesinlik ve ölçek belirtimini destekler.|  
|[COLUMN_NAME_TYPE_SIZE](#column_name_type_size)|Veritabanındaki belirli bir sütuna bağlama adına göre temsil eder. Veri türü ve boyut belirtimi destekler.|  
|[COLUMN_NAME_TYPE_STATUS](#column_name_type_status)|Veritabanındaki belirli bir sütuna bağlama adına göre temsil eder. Veri türü ve sütun durumu belirtimini destekler.|  
|[END_COLUMN_MAP](#end_column_map)|Sütun eşleme girişleri sonunu işaretler.|  
  
## <a name="command-macros"></a>Komut makroları  
  
|||  
|-|-|  
|[DEFINE_COMMAND](#define_command)|Satır kümesi kullanırken oluşturmak için kullanılacak komut belirtir [CCommand](../../data/oledb/ccommand-class.md) sınıfı. Yalnızca belirtilen uygulama türünü (ANSI veya Unicode) eşleşen dize türleri kabul eder. Kullanmanız önerilir [defıne_command_ex](../../data/oledb/define-command-ex.md) DEFINE_COMMAND yerine.|  
|[DEFINE_COMMAND_EX](#define_command_ex)|Satır kümesi kullanırken oluşturmak için kullanılacak komut belirtir [CCommand](../../data/oledb/ccommand-class.md) sınıfı. ANSI ve Unicode uygulamalarını destekler.|  
  
## <a name="parameter-map-macros"></a>Parametre eşleme makroları  
  
|||  
|-|-|  
|[BEGIN_PARAM_MAP](#begin_param_map)|Kullanıcı kayıt sınıfı parametre eşleme girişleri başlangıcını işaretler.|  
|[END_PARAM_MAP](#end_param_map)|Parametre eşleme girişleri sonunu işaretler.|  
|[SET_PARAM_TYPE](#set_param_type)|SET_PARAM_TYPE makrosu giriş, çıkış ve giriş/çıkış izleyin COLUMN_ENTRY makroları belirtir.|  

### <a name="atltraceerrorrecords"></a> AtlTraceErrorRecords
Bir hata döndürülürse, OLE DB hata kaydı bilgi döküm cihaza dökümünü yapar.  
  
#### <a name="syntax"></a>Sözdizimi  
  
```cpp
inline void AtlTraceErrorRecords(HRESULT hrErr = S_OK);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *hErr*  
 [in] Bir OLE DB tüketici şablonu üye işlevi tarafından döndürülen HRESULT.  
  
#### <a name="remarks"></a>Açıklamalar  
 Varsa *hErr* S_OK, değil `AtlTraceErrorRecords` OLE DB hata kaydı bilgi döküm cihaza dökümleri ( **hata ayıklama** sekmesine çıkış penceresine veya bir dosya). Sağlayıcıdan alınan hata kaydı bilgileri her bir hata kayıt girişi için satır numarası, kaynak, açıklama, Yardım dosyası, bağlam ve GUID içerir. `AtlTraceErrorRecords` Bu bilgileri yalnızca hata ayıklama dökümleri. Sürüm yapılandırmasında bu çıkış iyileştirilmiş boş bir saptama olur.  
  
#### <a name="see-also"></a>Ayrıca Bkz.    
 [CDBErrorInfo Sınıfı](../../data/oledb/cdberrorinfo-class.md)

### <a name="begin_accessor"></a> BEGIN_ACCESSOR
Bir erişimci giriş başlangıcına işaret eder.  
  
#### <a name="syntax"></a>Sözdizimi  
  
```cpp  
BEGIN_ACCESSOR(num, bAuto)  
```  
  
#### <a name="parameters"></a>Parametreler  
 *sayı*  
 [in] Bu erişimci harita erişimcisinde sıfır uzaklığı numarası.  
  
 *bDil*  
 [in] Bu erişimci erişimci otomatik veya el ile erişimci olup olmadığını belirtir. Varsa **true**, erişimci otomatik; ise **false**, erişimci el ile gerçekleştirilir. Otomatik erişimci, veri taşıma işlemleri sizin için alınmadığı anlamına gelir.  
  
#### <a name="remarks"></a>Açıklamalar  
 Üzerinde bir satır kümesinde çoklu erişimci söz konusu olduğunda BEGIN_ACCESSOR_MAP belirtin ve BEGIN_ACCESSOR makrosu kullanmak için tek tek her erişimci gerekir. BEGIN_ACCESSOR makrosu END_ACCESSOR makrosu ile tamamlanır. BEGIN_ACCESSOR_MAP makrosu END_ACCESSOR_MAP makrosu ile tamamlanır.  
  
#### <a name="example"></a>Örnek  
 Bkz: [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md).  

### <a name="begin_accessor_map"></a> BEGIN_ACCESSOR_MAP
Erişimci eşleme girişleri başlangıcını işaretler.  
  
#### <a name="syntax"></a>Sözdizimi  
  
```cpp  
BEGIN_ACCESSOR_MAP(x, num)  
```  
  
#### <a name="parameters"></a>Parametreler  
 *x*  
 [in] Kullanıcı kayıt sınıfı adı.  
  
 *sayı*  
 [in] Bu erişimci haritada erişimcileri sayısı.  
  
#### <a name="remarks"></a>Açıklamalar  
 Üzerinde bir satır kümesinde çoklu erişimci söz konusu olduğunda, başında BEGIN_ACCESSOR_MAP belirtin ve BEGIN_ACCESSOR makrosu kullanmak için tek tek her erişimci gerekir. BEGIN_ACCESSOR makrosu END_ACCESSOR makrosu ile tamamlanır. END_ACCESSOR_MAP makrosu ile erişimci harita tamamlandı.  
  
 Kullanıcı kaydına yalnızca bir erişimcisi varsa, makroyu kullanın [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md).  
  
#### <a name="example"></a>Örnek  

 ```cpp  
class CArtistsAccessor
{
public:
// Data Elements
   TCHAR m_szFirstName[21];
   TCHAR m_szLastName[31];
   short m_nAge;

// Output binding map
BEGIN_ACCESSOR_MAP(CArtistsAccessor, 2)
   BEGIN_ACCESSOR(0, true)
      COLUMN_ENTRY(1, m_szFirstName)
      COLUMN_ENTRY(2, m_szLastName)
   END_ACCESSOR()
   BEGIN_ACCESSOR(1, false) // Not an auto accessor
      COLUMN_ENTRY(3, m_nAge)
   END_ACCESSOR()
END_ACCESSOR_MAP()

   HRESULT OpenDataSource()
   {
      CDataSource _db;
      _db.Open();
      return m_session.Open(_db);
   }

   void CloseDataSource()
   {
      m_session.Close();
   }

   CSession m_session;

   DEFINE_COMMAND_EX(CArtistsAccessor, L" \
   SELECT \
      FirstName, \
      LastName, \
      Age \
      FROM Artists")
};
 ```

### <a name="end_accessor"></a> END_ACCESSOR
Bir erişimci girdinin sonunu işaretler.  
  
#### <a name="syntax"></a>Sözdizimi  
  
```cpp
END_ACCESSOR()  
```  
  
#### <a name="remarks"></a>Açıklamalar  
 Üzerinde bir satır kümesinde çoklu erişimci için BEGIN_ACCESSOR_MAP belirtin ve BEGIN_ACCESSOR makrosu kullanmak için tek tek her erişimci gerekir. BEGIN_ACCESSOR makrosu END_ACCESSOR makrosu ile tamamlanır. BEGIN_ACCESSOR_MAP makrosu END_ACCESSOR_MAP makrosu ile tamamlanır.  
  
#### <a name="example"></a>Örnek  
 Bkz: [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md).  

### <a name="end_accessor_map"></a> END_ACCESSOR_MAP
Erişimci eşleme girişleri sonunu işaretler.  
  
#### <a name="syntax"></a>Sözdizimi  
  
```cpp
END_ACCESSOR_MAP()  
```  
  
#### <a name="remarks"></a>Açıklamalar  
 Üzerinde bir satır kümesinde çoklu erişimci için BEGIN_ACCESSOR_MAP belirtin ve BEGIN_ACCESSOR makrosu kullanmak için tek tek her erişimci gerekir. BEGIN_ACCESSOR makrosu END_ACCESSOR makrosu ile tamamlanır. BEGIN_ACCESSOR_MAP makrosu END_ACCESSOR_MAP makrosu ile tamamlanır.  
  
#### <a name="example"></a>Örnek  
 Bkz: [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md).  

### <a name="begin_column_map"></a> BEGIN_COLUMN_MAP
Sütun eşleme girişi başlangıcını işaretler.  
  
#### <a name="syntax"></a>Sözdizimi  
  
```cpp  
BEGIN_COLUMN_MAP(x)  
```  
  
#### <a name="parameters"></a>Parametreler  
 *x*  
 [in] Kullanıcı kayıt sınıfı adını türetilen `CAccessor`.  
  
#### <a name="remarks"></a>Açıklamalar  
 Bu makro, bir satır kümesi üzerinde tek bir erişimci söz konusu olduğunda kullanılır. Satır kümesinde çoklu erişimci varsa, [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md).  
  
 BEGIN_COLUMN_MAP makrosu END_COLUMN_MAP makrosu ile tamamlanır. Bu makro, yalnızca bir erişimci kullanıcı kaydında gerekli olduğunda kullanılır.  
  
 Sütunları bağlamak istediğiniz satır kümesi içindeki alanlara karşılık gelir.  
  
#### <a name="example"></a>Örnek  
 Bir örnek sütun ve parametre eşlemesi şu şekildedir:  
  
 <!--[!CODE [NVC_OLEDB_Consumer#16](../codesnippet/vs_snippets_cpp/nvc_oledb_consumer#16)]  -->

### <a name="blob_entry"></a> BLOB_ENTRY
BEGIN_COLUMN_MAP ve END_COLUMN_MAP ikili büyük nesne bağlamak için kullanılan ([BLOB](https://msdn.microsoft.com/library/ms711511.aspx)).  
  
#### <a name="syntax"></a>Sözdizimi  
  
```cpp
BLOB_ENTRY(nOrdinal, IID, flags, data)  
```  
  
#### <a name="parameters"></a>Parametreler  
 *nOrdinal*  
 [in] Sütun numarası.  
  
 *IID*  
 [in] GUID gibi arabirim `IDD_ISequentialStream`BLOB almak için kullanılır.  
  
 *bayrakları*  
 [in] Depolama modu bayrakları OLE yapılı depolama modeli tarafından tanımlandığı şekilde (örneğin, `STGM_READ`).  
  
 *Veri*  
 [in] Kullanıcı kaydındaki karşılık gelen veri üyesi.  
  
#### <a name="example"></a>Örnek  
 Bkz: [nasıl miyim alabilir BLOB?](../../data/oledb/retrieving-a-blob.md).  

### <a name="blob_entry_length"></a> BLOB_ENTRY_LENGTH
BEGIN_COLUMN_MAP ve END_COLUMN_MAP ikili büyük nesne bağlamak için kullanılan ([BLOB](https://msdn.microsoft.com/library/ms711511.aspx)). Benzer şekilde [BLOB_ENTRY](../../data/oledb/blob-entry.md)dışında bu makroyu ayrıca BLOB sütun bayt cinsinden uzunluğu alır.  
  
#### <a name="syntax"></a>Sözdizimi  
  
```cpp
BLOB_ENTRY_LENGTH(nOrdinal, IID, flags, data, length)  
```  
  
#### <a name="parameters"></a>Parametreler  
 *nOrdinal*  
 [in] Sütun numarası.  
  
 *IID*  
 [in] GUID gibi arabirim `IDD_ISequentialStream`BLOB almak için kullanılır.  
  
 *bayrakları*  
 [in] Depolama modu bayrakları OLE yapılı depolama modeli tarafından tanımlandığı şekilde (örneğin, `STGM_READ`).  
  
 *Veri*  
 [in] Kullanıcı kaydındaki karşılık gelen veri üyesi.  
  
 *Uzunluğu*  
 [out] Bayt cinsinden BLOB sütun (gerçek) uzunluğu.  
  
#### <a name="example"></a>Örnek  
 Bkz: [nasıl miyim alabilir BLOB?](../../data/oledb/retrieving-a-blob.md).  

### <a name="blob_entry_length_status"></a> BLOB_ENTRY_LENGTH_STATUS
BEGIN_COLUMN_MAP ve END_COLUMN_MAP ikili büyük nesne bağlamak için kullanılan ([BLOB](https://msdn.microsoft.com/library/ms711511.aspx)). Benzer şekilde [BLOB_ENTRY](../../data/oledb/blob-entry.md)dışında bu makro uzunluğu ve BLOB sütununu durumunu alır.  
  
#### <a name="syntax"></a>Sözdizimi  
  
```cpp
BLOB_ENTRY_LENGTH_STATUS(  
    nOrdinal,  
    IID,  
    flags,  
    data,
    length,
    status )  
```  
  
#### <a name="parameters"></a>Parametreler  
 *nOrdinal*  
 [in] Sütun numarası.  
  
 *IID*  
 [in] GUID gibi arabirim `IDD_ISequentialStream`BLOB almak için kullanılır.  
  
 *bayrakları*  
 [in] Depolama modu bayrakları OLE yapılı depolama modeli tarafından tanımlandığı şekilde (örneğin, `STGM_READ`).  
  
 *Veri*  
 [in] Kullanıcı kaydındaki karşılık gelen veri üyesi.  
  
 *Uzunluğu*  
 [out] Bayt cinsinden BLOB sütun (gerçek) uzunluğu.  
  
 *Durumu*  
 [out] BLOB veri sütununun durumu.  
  
#### <a name="example"></a>Örnek  
 Bkz: [nasıl miyim alabilir BLOB?](../../data/oledb/retrieving-a-blob.md).  

### <a name="blob_entry_status"></a> BLOB_ENTRY_STATUS
BEGIN_COLUMN_MAP veya BEGIN_ACCESSOR_MAP ikili büyük nesne bağlamak için kullanılan ([BLOB](https://msdn.microsoft.com/library/ms711511.aspx)). Benzer şekilde [BLOB_ENTRY](../../data/oledb/blob-entry.md)dışında bu makroyu BLOB sütununu durumunu da alır.  
  
#### <a name="syntax"></a>Sözdizimi  
  
```cpp
BLOB_ENTRY_STATUS(nOrdinal, IID, flags, data, status)   
```  
  
#### <a name="parameters"></a>Parametreler  
 *nOrdinal*  
 [in] Sütun numarası.  
  
 *IID*  
 [in] GUID gibi arabirim `IDD_ISequentialStream`BLOB almak için kullanılır.  
  
 *bayrakları*  
 [in] Depolama modu bayrakları OLE yapılı depolama modeli tarafından tanımlandığı şekilde (örneğin, `STGM_READ`).  
  
 *Veri*  
 [in] Kullanıcı kaydındaki karşılık gelen veri üyesi.  
  
 *Durumu*  
 [out] BLOB alan durumu.  
  
#### <a name="example"></a>Örnek  
 Bkz: [nasıl miyim alabilir BLOB?](../../data/oledb/retrieving-a-blob.md).  

### <a name="blob_name"></a> BLOB_NAME
BEGIN_COLUMN_MAP ve END_COLUMN_MAP ikili büyük nesne bağlamak için kullanılan ([BLOB](https://msdn.microsoft.com/library/ms711511.aspx)). Benzer şekilde [BLOB_ENTRY](../../data/oledb/blob-entry.md)dışında bu makroyu bir sütun numarası yerine sütun adını alır.  
  
#### <a name="syntax"></a>Sözdizimi  
  
```cpp
BLOB_NAME(pszName, IID, flags, data )  
```  
  
#### <a name="parameters"></a>Parametreler  
 *pszName*  
 [in] Sütun adı için bir işaretçi. Adı bir Unicode dize olması gerekir. Bu örneğin adının önüne bir 'L' koyarak gerçekleştirebilirsiniz: `L"MyColumn"`.  
  
 *IID*  
 [in] GUID gibi arabirim `IDD_ISequentialStream`BLOB almak için kullanılır.  
  
 *bayrakları*  
 [in] Depolama modu bayrakları OLE yapılı depolama modeli tarafından tanımlandığı şekilde (örneğin, `STGM_READ`).  
  
 *Veri*  
 [in] Kullanıcı kaydındaki karşılık gelen veri üyesi.  
  
#### <a name="example"></a>Örnek  
 Bkz: [nasıl miyim alabilir BLOB?](../../data/oledb/retrieving-a-blob.md).  

### <a name="blob_name_length"></a> BLOB_NAME_LENGTH
BEGIN_COLUMN_MAP ve END_COLUMN_MAP ikili büyük nesne bağlamak için kullanılan ([BLOB](https://msdn.microsoft.com/library/ms711511.aspx)). Benzer şekilde [BLOB_NAME](../../data/oledb/blob-name.md)dışında bu makroyu ayrıca BLOB veri sütununun bayt cinsinden uzunluğu alır.  
  
#### <a name="syntax"></a>Sözdizimi  
  
```cpp
BLOB_NAME_LENGTH(pszName, IID, flags, data, length )  
```  
  
#### <a name="parameters"></a>Parametreler  
 *pszName*  
 [in] Sütun adı için bir işaretçi. Adı bir Unicode dize olması gerekir. Bu örneğin adının önüne bir 'L' koyarak gerçekleştirebilirsiniz: `L"MyColumn"`.  
  
 *IID*  
 [in] GUID gibi arabirim `IDD_ISequentialStream`BLOB almak için kullanılır.  
  
 *bayrakları*  
 [in] Depolama modu bayrakları OLE yapılı depolama modeli tarafından tanımlandığı şekilde (örneğin, `STGM_READ`).  
  
 *Veri*  
 [in] Kullanıcı kaydındaki karşılık gelen veri üyesi.  
  
 *Uzunluğu*  
 [out] Bayt cinsinden BLOB sütun (gerçek) uzunluğu.  

### <a name="blob_name_length_status"></a> BLOB_NAME_LENGTH_STATUS
BEGIN_COLUMN_MAP ve END_COLUMN_MAP ikili büyük nesne bağlamak için kullanılan ([BLOB](https://msdn.microsoft.com/library/ms711511.aspx)). Benzer şekilde [BLOB_NAME](../../data/oledb/blob-name.md)dışında bu makro uzunluğu ve BLOB veri sütununu durumunu alır.  
  
#### <a name="syntax"></a>Sözdizimi  
  
```cpp
BLOB_NAME_LENGTH_STATUS(pszName, IID, flags, data, length, status )  
```  
  
#### <a name="parameters"></a>Parametreler  
 *pszName*  
 [in] Sütun adı için bir işaretçi. Adı bir Unicode dize olması gerekir. Bu örneğin adının önüne bir 'L' koyarak gerçekleştirebilirsiniz: `L"MyColumn"`.  
  
 *IID*  
 [in] GUID gibi arabirim `IDD_ISequentialStream`BLOB almak için kullanılır.  
  
 *bayrakları*  
 [in] Depolama modu bayrakları OLE yapılı depolama modeli tarafından tanımlandığı şekilde (örneğin, `STGM_READ`).  
  
 *Veri*  
 [in] Kullanıcı kaydındaki karşılık gelen veri üyesi.  
  
 *Uzunluğu*  
 [out] Bayt cinsinden BLOB sütun (gerçek) uzunluğu.  
  
 *Durumu*  
 [out] BLOB alan durumu.  

### <a name="blob_name_status"></a> BLOB_NAME_STATUS
BEGIN_COLUMN_MAP ve END_COLUMN_MAP ikili büyük nesne bağlamak için kullanılan ([BLOB](https://msdn.microsoft.com/library/ms711511.aspx)). Benzer şekilde [BLOB_NAME](../../data/oledb/blob-name.md)dışında bu makroyu BLOB veri sütununu durumunu da alır.  
  
#### <a name="syntax"></a>Sözdizimi  
  
```cpp
BLOB_NAME_STATUS(pszName, IID, flags, data, status )  
```  
  
#### <a name="parameters"></a>Parametreler  
 *pszName*  
 [in] Sütun adı için bir işaretçi. Adı bir Unicode dize olması gerekir. Bu örneğin adının önüne bir 'L' koyarak gerçekleştirebilirsiniz: `L"MyColumn"`.  
  
 *IID*  
 [in] GUID gibi arabirim `IDD_ISequentialStream`BLOB almak için kullanılır.  
  
 *bayrakları*  
 [in] Depolama modu bayrakları OLE yapılı depolama modeli tarafından tanımlandığı şekilde (örneğin, `STGM_READ`).  
  
 *Veri*  
 [in] Kullanıcı kaydındaki karşılık gelen veri üyesi.  
  
 *Durumu*  
 [out] BLOB alan durumu.  
  
### <a name="bookmark_entry"></a> BOOKMARK_ENTRY
Yer işareti sütunu bağlar.  
  
#### <a name="syntax"></a>Sözdizimi  
  
```cpp
BOOKMARK_ENTRY(variable)  
```  
  
#### <a name="parameters"></a>Parametreler  
 *Değişkeni*  
 [in] Yer işareti sütunu bağlanması için değişken.  
  
#### <a name="example"></a>Örnek  

```cpp  
class CArtistsBookmark
{
public:
// Data Elements
   CBookmark<4> m_bookmark;
   short m_nAge;
   TCHAR m_szFirstName[21];
   TCHAR m_szLastName[31];

// Output binding map
BEGIN_COLUMN_MAP(CArtistsBookmark)
   BOOKMARK_ENTRY(m_bookmark)
   COLUMN_ENTRY(1, m_nAge)
   COLUMN_ENTRY(2, m_szFirstName)
   COLUMN_ENTRY(3, m_szLastName)
END_COLUMN_MAP()

   void GetRowsetProperties(CDBPropSet* pPropSet)
   {
      pPropSet->AddProperty(DBPROP_BOOKMARKS, true);
   }

   HRESULT OpenDataSource()
   {
      CDataSource _db;
      _db.Open();
      return m_session.Open(_db);
   }

   void CloseDataSource()
   {
      m_session.Close();
   }

   CSession m_session;

   DEFINE_COMMAND_EX(CArtistsBookmark, L" \
   SELECT \
      Age, \
      FirstName, \
      LastName \
      FROM Artists")
};
```
  
#### <a name="see-also"></a>Ayrıca Bkz.  
 [CBookmark sınıfı](../../data/oledb/cbookmark-class.md)   
 [DBPROP_BOOKMARKS](https://msdn.microsoft.com/library/ms709728.aspx)

### <a name="column_entry"></a> COLUMN_ENTRY
Satır kümesi üzerindeki bir bağlamaya satır kümesindeki belirli bir sütunu temsil eder.  
  
#### <a name="syntax"></a>Sözdizimi  
  
```cpp
COLUMN_ENTRY(nOrdinal, data)  
```  
  
#### <a name="parameters"></a>Parametreler  
 Bkz: [IAccessor::CreateAccessor'ı](https://msdn.microsoft.com/library/ms716845.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
 *nOrdinal*  
 [in] Sütun numarası.  
  
 *Veri*  
 [in] Kullanıcı kaydındaki karşılık gelen veri üyesi.  
  
#### <a name="remarks"></a>Açıklamalar  
 COLUMN_ENTRY makrosu, aşağıdaki konumlarda kullanılır:  
  
-   Arasında [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) ve [END_COLUMN_MAP](../../data/oledb/end-column-map.md) makroları.  
  
-   Arasında [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) ve [END_ACCESSOR](../../data/oledb/end-accessor.md) makroları.  
  
-   Arasında [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) ve [END_PARAM_MAP](../../data/oledb/end-param-map.md) makroları.  
  
#### <a name="example"></a>Örnek  
 Makro konulardaki örnekleri görmek [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) ve [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md).  

### <a name="column_entry_ex"></a> COLUMN_ENTRY_EX
Satır kümesi üzerindeki bir bağlamaya, veritabanında belirli bir sütunu temsil eder.  
  
#### <a name="syntax"></a>Sözdizimi  
  
```cpp
COLUMN_ENTRY_EX(nOrdinal, wType, nLength, nPrecision, nScale, data, length, status)  
```  
  
#### <a name="parameters"></a>Parametreler  
 Bkz: [IAccessor::CreateAccessor'ı](https://msdn.microsoft.com/library/ms716845.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
 *nOrdinal*  
 [in] Sütun numarası.  
  
 *wType*  
 [in] Veri türü.  
  
 *nLength*  
 [in] Bayt cinsinden veri boyutu.  
  
 *nPrecision*  
 [in] Veri alma sırasında kullanılacak en fazla kesinlik ve *wType* olduğu `DBTYPE_NUMERIC`. Aksi takdirde, bu parametre yoksayılır.  
  
 *nScale*  
 [in] Veri alınırken kullanılacak ölçek ve *wType* olduğu `DBTYPE_NUMERIC` veya `DBTYPE_DECIMAL`.  
  
 *Veri*  
 [in] Kullanıcı kaydındaki karşılık gelen veri üyesi.  
  
 *Uzunluğu*  
 [in] Sütun uzunluğu için bağlanacak değişkeni.  
  
 *Durumu*  
 [in] Sütun durumuna bağlı değişken.  
  
#### <a name="remarks"></a>Açıklamalar  
 COLUMN_ENTRY_EX makrosu, aşağıdaki konumlarda kullanılır:  
  
-   Arasında [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) ve [END_COLUMN_MAP](../../data/oledb/end-column-map.md) makroları.  
  
-   Arasında [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) ve [END_ACCESSOR](../../data/oledb/end-accessor.md) makroları.  
  
-   Arasında [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) ve [END_PARAM_MAP](../../data/oledb/end-param-map.md) makroları.  
  
#### <a name="example"></a>Örnek  
 Bkz: [BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md).  

### <a name="column_entry_length"></a> COLUMN_ENTRY_LENGTH
Satır kümesi üzerindeki bir bağlamaya, veritabanında belirli bir sütunu temsil eder.  
  
#### <a name="syntax"></a>Sözdizimi  
  
```cpp
COLUMN_ENTRY_LENGTH(nOrdinal, data, length)  
```  
  
#### <a name="parameters"></a>Parametreler  
 Bkz: [IAccessor::CreateAccessor'ı](https://msdn.microsoft.com/library/ms716845.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
 *nOrdinal*  
 [in] İle başlayarak sütun numarası. Yer işareti sıfır sütununa karşılık gelir.  
  
 *Veri*  
 [in] Kullanıcı kaydındaki karşılık gelen veri üyesi.  
  
 *Uzunluğu*  
 [in] Sütun uzunluğu için bağlanacak değişkeni.  
  
#### <a name="remarks"></a>Açıklamalar  
 Bu makro destekler *uzunluğu* değişkeni. Aşağıdaki konumlarda kullanılır:  
  
-   Arasında [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) ve [END_COLUMN_MAP](../../data/oledb/end-column-map.md) makroları.  
  
-   Arasında [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) ve [END_ACCESSOR](../../data/oledb/end-accessor.md) makroları.  
  
-   Arasında [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) ve [END_PARAM_MAP](../../data/oledb/end-param-map.md) makroları.  
  
### <a name="column_entry_length_status"></a> COLUMN_ENTRY_LENGTH_STATUS
Satır kümesi üzerindeki bir bağlamaya, veritabanında belirli bir sütunu temsil eder.  
  
#### <a name="syntax"></a>Sözdizimi  
  
```cpp
COLUMN_ENTRY_LENGTH_STATUS(nOrdinal, data, length, status)  
```  
  
#### <a name="parameters"></a>Parametreler  
 Bkz: [IAccessor::CreateAccessor'ı](https://msdn.microsoft.com/library/ms716845.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
 *nOrdinal*  
 [in] Sütun numarası.  
  
 *Veri*  
 [in] Kullanıcı kaydındaki karşılık gelen veri üyesi.  
  
 *Uzunluğu*  
 [in] Sütun uzunluğu için bağlanacak değişkeni.  
  
 *Durumu*  
 [in] Sütun durumuna bağlı değişken.  
  
#### <a name="remarks"></a>Açıklamalar  
 Bu makro, uzunluğu ve durumu değişkenlerini destekle istediğinizde kullanın. Aşağıdaki konumlarda kullanılır:  
  
-   Arasında [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) ve [END_COLUMN_MAP](../../data/oledb/end-column-map.md) makroları.  
  
-   Arasında [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) ve [END_ACCESSOR](../../data/oledb/end-accessor.md) makroları.  
  
-   Arasında [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) ve [END_PARAM_MAP](../../data/oledb/end-param-map.md) makroları.  

### <a name="column_entry_ps"></a> COLUMN_ENTRY_PS
Satır kümesi üzerindeki bir bağlamaya satır kümesindeki belirli bir sütunu temsil eder.  
  
#### <a name="syntax"></a>Sözdizimi  
  
```cpp
COLUMN_ENTRY_PS(nOrdinal, nPrecision, nScale, data)  
```  
  
#### <a name="parameters"></a>Parametreler  
 Bkz: [IAccessor::CreateAccessor'ı](https://msdn.microsoft.com/library/ms716845.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
 *nOrdinal*  
 [in] Sütun numarası.  
  
 *nPrecision*  
 [in] Verilen duyarlık bağlamak istediğiniz sütun.  
  
 *nScale*  
 [in] Ölçeğin bağlamak istediğiniz sütun.  
  
 *Veri*  
 [in] Kullanıcı kaydındaki karşılık gelen veri üyesi.  
  
#### <a name="remarks"></a>Açıklamalar  
 Kesinlik ve ölçek bağlamak istediğiniz sütunun belirtmenizi sağlar. Aşağıdaki konumlarda kullanılır:  
  
-   Arasında [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) ve [END_COLUMN_MAP](../../data/oledb/end-column-map.md) makroları.  
  
-   Arasında [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) ve [END_ACCESSOR](../../data/oledb/end-accessor.md) makroları.  
  
-   Arasında [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) ve [END_PARAM_MAP](../../data/oledb/end-param-map.md) makroları.  

### <a name="column_entry_ps_length"></a> COLUMN_ENTRY_PS_LENGTH
Satır kümesi üzerindeki bir bağlamaya, veritabanında belirli bir sütunu temsil eder.  
  
#### <a name="syntax"></a>Sözdizimi  
  
```cpp
COLUMN_ENTRY_PS_LENGTH(nOrdinal, nPrecision, nScale, data, length)  
```  
  
#### <a name="parameters"></a>Parametreler  
 Bkz: [IAccessor::CreateAccessor'ı](https://msdn.microsoft.com/library/ms716845.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
 *nOrdinal*  
 [in] İle başlayarak sütun numarası. Yer işareti sıfır sütununa karşılık gelir.  
  
 *nPrecision*  
 [in] Verilen duyarlık bağlamak istediğiniz sütun.  
  
 *nScale*  
 [in] Ölçeğin bağlamak istediğiniz sütun.  
  
 *Veri*  
 [in] Kullanıcı kaydındaki karşılık gelen veri üyesi.  
  
 *Uzunluğu*  
 [in] Sütun uzunluğu için bağlanacak değişkeni.  
  
#### <a name="remarks"></a>Açıklamalar  
 Kesinlik ve ölçek bağlamak istediğiniz sütunun belirtmenizi sağlar. Bu makro destekler *uzunluğu* değişkeni. Aşağıdaki konumlarda kullanılır:  
  
-   Arasında [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) ve [END_COLUMN_MAP](../../data/oledb/end-column-map.md) makroları.  
  
-   Arasında [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) ve [END_ACCESSOR](../../data/oledb/end-accessor.md) makroları.  
  
-   Arasında [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) ve [END_PARAM_MAP](../../data/oledb/end-param-map.md) makroları.  

### <a name="column_entry_ps_length_status"></a> COLUMN_ENTRY_PS_LENGTH_STATUS
Satır kümesi üzerindeki bir bağlamaya, veritabanında belirli bir sütunu temsil eder.  
  
#### <a name="syntax"></a>Sözdizimi  
  
```cpp
COLUMN_ENTRY_PS_LENGTH_STATUS(nOrdinal, nPrecision, nScale, data, length, status)  
```  
  
#### <a name="parameters"></a>Parametreler  
 Bkz: [IAccessor::CreateAccessor'ı](https://msdn.microsoft.com/library/ms716845.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
 *nOrdinal*  
 [in] Sütun numarası.  
  
 *nPrecision*  
 [in] Verilen duyarlık bağlamak istediğiniz sütun.  
  
 *nScale*  
 [in] Ölçeğin bağlamak istediğiniz sütun.  
  
 *Veri*  
 [in] Kullanıcı kaydındaki karşılık gelen veri üyesi.  
  
 *Uzunluğu*  
 [in] Sütun uzunluğu için bağlanacak değişkeni.  
  
 *Durumu*  
 [in] Sütun durumuna bağlı değişken.  
  
#### <a name="remarks"></a>Açıklamalar  
 Kesinlik ve ölçek bağlamak istediğiniz sütunun belirtmenizi sağlar. Bu makro, uzunluğu ve durumu değişkenlerini destekle istediğinizde kullanın. Aşağıdaki konumlarda kullanılır:  
  
-   Arasında [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) ve [END_COLUMN_MAP](../../data/oledb/end-column-map.md) makroları.  
  
-   Arasında [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) ve [END_ACCESSOR](../../data/oledb/end-accessor.md) makroları.  
  
-   Arasında [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) ve [END_PARAM_MAP](../../data/oledb/end-param-map.md) makroları.  

### <a name="column_entry_ps_status"></a> COLUMN_ENTRY_PS_STATUS
Satır kümesi üzerindeki bir bağlamaya, veritabanında belirli bir sütunu temsil eder.  
  
#### <a name="syntax"></a>Sözdizimi  
  
```cpp
COLUMN_ENTRY_PS_STATUS(nOrdinal, nPrecision, nScale, data, status)  
```  
  
#### <a name="parameters"></a>Parametreler  
 Bkz: [IAccessor::CreateAccessor'ı](https://msdn.microsoft.com/library/ms716845.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
 *nOrdinal*  
 [in] Sütun numarası.  
  
 *nPrecision*  
 [in] Verilen duyarlık bağlamak istediğiniz sütun.  
  
 *nScale*  
 [in] Ölçeğin bağlamak istediğiniz sütun.  
  
 *Veri*  
 [in] Kullanıcı kaydındaki karşılık gelen veri üyesi.  
  
 *Durumu*  
 [in] Sütun durumuna bağlı değişken.  
  
#### <a name="remarks"></a>Açıklamalar  
 Kesinlik ve ölçek bağlamak istediğiniz sütunun belirtmenizi sağlar. Bu makro destekler *durumu* değişkeni. Aşağıdaki konumlarda kullanılır:  
  
-   Arasında [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) ve [END_COLUMN_MAP](../../data/oledb/end-column-map.md) makroları.  
  
-   Arasında [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) ve [END_ACCESSOR](../../data/oledb/end-accessor.md) makroları.  
  
-   Arasında [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) ve [END_PARAM_MAP](../../data/oledb/end-param-map.md) makroları.  
  
### <a name="column_entry_status"></a> COLUMN_ENTRY_STATUS
Satır kümesi üzerindeki bir bağlamaya, veritabanında belirli bir sütunu temsil eder.  
  
#### <a name="syntax"></a>Sözdizimi  
  
```cpp
COLUMN_ENTRY_STATUS(nOrdinal, data, status)  
```  
  
#### <a name="parameters"></a>Parametreler  
 Bkz: [IAccessor::CreateAccessor'ı](https://msdn.microsoft.com/library/ms716845.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
 *nOrdinal*  
 [in] Sütun numarası.  
  
 *Veri*  
 [in] Kullanıcı kaydındaki karşılık gelen veri üyesi.  
  
 *Durumu*  
 [in] Sütun durumuna bağlı değişken.  
  
#### <a name="remarks"></a>Açıklamalar  
 Bu makro destekler *durumu* değişkeni. Aşağıdaki konumlarda kullanılır:  
  
-   Arasında [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) ve [END_COLUMN_MAP](../../data/oledb/end-column-map.md) makroları.  
  
-   Arasında [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) ve [END_ACCESSOR](../../data/oledb/end-accessor.md) makroları.  
  
-   Arasında [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) ve [END_PARAM_MAP](../../data/oledb/end-param-map.md) makroları.  

### <a name="column_entry_type"></a> COLUMN_ENTRY_TYPE
Veritabanındaki belirli bir sütuna bağlama temsil eder. Destekler *türü* parametresi.  
  
#### <a name="syntax"></a>Sözdizimi  
  
```cpp
COLUMN_ENTRY_TYPE (nOrdinal, wType, data)  
```  
  
#### <a name="parameters"></a>Parametreler  
 *nOrdinal*  
 [in] Sütun numarası.  
  
 *wType*  
 [in] Sütun giriş veri türü.  
  
 *Veri*  
 [in] Kullanıcı kaydındaki karşılık gelen veri üyesi.  
  
#### <a name="remarks"></a>Açıklamalar  
 Bu makro bir özelleştirilmiş çeşididir [COLUMN_ENTRY](../../data/oledb/column-entry.md) makro veri türünü belirten bir yol sağlar.  

### <a name="column_entry_type_size"></a> COLUMN_ENTRY_TYPE_SIZE
Veritabanındaki belirli bir sütuna bağlama temsil eder. Destekler *türü* ve *boyutu* parametreleri.  
  
#### <a name="syntax"></a>Sözdizimi  
  
```cpp
COLUMN_ENTRY_TYPE_SIZE(nOrdinal, wType, nLength, data)  
```  
  
#### <a name="parameters"></a>Parametreler  
 *nOrdinal*  
 [in] Sütun numarası.  
  
 *wType*  
 [in] Sütun giriş veri türü.  
  
 *nLength*  
 [in] Sütun giriş bayt cinsinden boyutu.  
  
 *Veri*  
 [in] Kullanıcı kaydındaki karşılık gelen veri üyesi.  
  
#### <a name="remarks"></a>Açıklamalar  
 Bu makro bir özelleştirilmiş çeşididir [COLUMN_ENTRY](../../data/oledb/column-entry.md) makro veri boyutunu ve türünü belirten bir yol sağlar.  

### <a name="column_name"></a> COLUMN_NAME
Satır kümesi üzerindeki bir bağlamaya satır kümesindeki belirli bir sütunu temsil eder. Benzer şekilde [COLUMN_ENTRY](../../data/oledb/column-entry.md)dışında bu makroyu sütun numarası yerine sütun adını alır.  
  
#### <a name="syntax"></a>Sözdizimi  
  
```cpp
COLUMN_NAME(pszName, data)  
```  
  
#### <a name="parameters"></a>Parametreler  
 *pszName*  
 [in] Sütun adı için bir işaretçi. Adı bir Unicode dize olması gerekir. Bu örneğin adının önüne bir 'L' koyarak gerçekleştirebilirsiniz: `L"MyColumn"`.  
  
 *Veri*  
 [in] Kullanıcı kaydındaki karşılık gelen veri üyesi.  
  
#### <a name="remarks"></a>Açıklamalar  
 COLUMN_NAME_ * makroları aynı yerde kullanılan [COLUMN_ENTRY](../../data/oledb/column-entry.md):  
  
-   Arasında [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) ve [END_COLUMN_MAP](../../data/oledb/end-column-map.md) makroları.  
  
-   Arasında [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) ve [END_ACCESSOR](../../data/oledb/end-accessor.md) makroları.  
  
-   Arasında [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) ve [END_PARAM_MAP](../../data/oledb/end-param-map.md) makroları.  

### <a name="column_name_ex"></a> COLUMN_NAME_EX
Satır kümesi üzerindeki bir bağlamaya satır kümesindeki belirli bir sütunu temsil eder. Benzer şekilde [COLUMN_NAME](../../data/oledb/column-name.md)dışında bu makroyu veri türü, boyut, duyarlık, Ölçek, sütun uzunluğu ve sütun durumunu alır.  
  
#### <a name="syntax"></a>Sözdizimi  
  
```cpp
COLUMN_NAME_EX(pszName, wType, nLength, nPrecision, nScale, data, length, status )  
```  
  
#### <a name="parameters"></a>Parametreler  
 *pszName*  
 [in] Sütun adı için bir işaretçi. Adı bir Unicode dize olması gerekir. Bu örneğin adının önüne bir 'L' koyarak gerçekleştirebilirsiniz: `L"MyColumn"`.  
  
 *wType*  
 [in] Veri türü.  
  
 *nLength*  
 [in] Bayt cinsinden veri boyutu.  
  
 *nPrecision*  
 [in] Veri alma sırasında kullanılacak en fazla kesinlik ve *wType* olduğu `DBTYPE_NUMERIC`. Aksi takdirde, bu parametre yoksayılır.  
  
 *nScale*  
 [in] Veri alınırken kullanılacak ölçek ve *wType* olduğu `DBTYPE_NUMERIC` veya `DBTYPE_DECIMAL`.  
  
 *Veri*  
 [in] Kullanıcı kaydındaki karşılık gelen veri üyesi.  
  
 *Uzunluğu*  
 [in] Sütun uzunluğu için bağlanacak değişkeni.  
  
 *Durumu*  
 [in] Sütun durumuna bağlı değişken.  
  
#### <a name="remarks"></a>Açıklamalar  
 Bkz: [COLUMN_NAME](../../data/oledb/column-name.md) COLUMN_NAME_ * makroları kullanıldığı hakkında bilgi.  

### <a name="column_name_length"></a> COLUMN_NAME_LENGTH
Satır kümesi üzerindeki bir bağlamaya satır kümesindeki belirli bir sütunu temsil eder. Benzer şekilde [COLUMN_NAME](../../data/oledb/column-name.md)dışında bu makroyu Ayrıca sütun uzunluğunu alır.  
  
#### <a name="syntax"></a>Sözdizimi  
  
```cpp
COLUMN_NAME_LENGTH(pszName, data, length)  
```  
  
#### <a name="parameters"></a>Parametreler  
 *pszName*  
 [in] Sütun adı için bir işaretçi. Adı bir Unicode dize olması gerekir. Bu örneğin adının önüne bir 'L' koyarak gerçekleştirebilirsiniz: `L"MyColumn"`.  
  
 *Veri*  
 [in] Kullanıcı kaydındaki karşılık gelen veri üyesi.  
  
 *Uzunluğu*  
 [in] Sütun uzunluğu için bağlanacak değişkeni.  
  
#### <a name="remarks"></a>Açıklamalar  
 Bkz: [COLUMN_NAME](../../data/oledb/column-name.md) COLUMN_NAME_ * makroları kullanıldığı hakkında bilgi.  

### <a name="column_name_length_status"></a> COLUMN_NAME_LENGTH_STATUS
Satır kümesi üzerindeki bir bağlamaya satır kümesindeki belirli bir sütunu temsil eder. Benzer şekilde [COLUMN_NAME](../../data/oledb/column-name.md)dışında bu makroyu sütun uzunluğu ve sütun durumunu alır.  
  
#### <a name="syntax"></a>Sözdizimi  
  
```cpp
COLUMN_NAME_LENGTH_STATUS(pszName, data, length, status )  
```  
  
#### <a name="parameters"></a>Parametreler  
 *pszName*  
 [in] Sütun adı için bir işaretçi. Adı bir Unicode dize olması gerekir. Bu örneğin adının önüne bir 'L' koyarak gerçekleştirebilirsiniz: `L"MyColumn"`.  
  
 *Veri*  
 [in] Kullanıcı kaydındaki karşılık gelen veri üyesi.  
  
 *Uzunluğu*  
 [in] Sütun uzunluğu için bağlanacak değişkeni.  
  
 *Durumu*  
 [in] Sütun durumuna bağlı değişken.  
  
#### <a name="remarks"></a>Açıklamalar  
 Bkz: [COLUMN_NAME](../../data/oledb/column-name.md) COLUMN_NAME_ * makroları kullanıldığı hakkında bilgi.  

### <a name="column_name_ps"></a> COLUMN_NAME_PS
Satır kümesi üzerindeki bir bağlamaya satır kümesindeki belirli bir sütunu temsil eder. Benzer şekilde [COLUMN_NAME](../../data/oledb/column-name.md)dışında bu makroyu kesinlik ve ölçek alır.  
  
#### <a name="syntax"></a>Sözdizimi  
  
```cpp
COLUMN_NAME_PS(pszName, nPrecision, nScale, data )  
```  
  
#### <a name="parameters"></a>Parametreler  
 *pszName*  
 [in] Sütun adı için bir işaretçi. Adı bir Unicode dize olması gerekir. Bu örneğin adının önüne bir 'L' koyarak gerçekleştirebilirsiniz: `L"MyColumn"`.  
  
 *nPrecision*  
 [in] Verilen duyarlık bağlamak istediğiniz sütun.  
  
 *nScale*  
 [in] Ölçeğin bağlamak istediğiniz sütun.  
  
 *Veri*  
 [in] Kullanıcı kaydındaki karşılık gelen veri üyesi.  
  
#### <a name="remarks"></a>Açıklamalar  
 Bkz: [COLUMN_NAME](../../data/oledb/column-name.md) COLUMN_NAME_ * makroları kullanıldığı hakkında bilgi.  

### <a name="column_name_ps_length"></a> COLUMN_NAME_PS_LENGTH
Satır kümesi üzerindeki bir bağlamaya satır kümesindeki belirli bir sütunu temsil eder. Benzer şekilde [COLUMN_NAME](../../data/oledb/column-name.md)dışında bu makroyu ayrıca kesinlik ve ölçek sütun uzunluğu alır.  
  
#### <a name="syntax"></a>Sözdizimi  
  
```cpp
COLUMN_NAME_PS_LENGTH(pszName, nPrecision, nScale, data, length )  
```  
  
#### <a name="parameters"></a>Parametreler  
 *pszName*  
 [in] Sütun adı için bir işaretçi. Adı bir Unicode dize olması gerekir. Bu örneğin adının önüne bir 'L' koyarak gerçekleştirebilirsiniz: `L"MyColumn"`.  
  
 *nPrecision*  
 [in] Verilen duyarlık bağlamak istediğiniz sütun.  
  
 *nScale*  
 [in] Ölçeğin bağlamak istediğiniz sütun.  
  
 *Veri*  
 [in] Kullanıcı kaydındaki karşılık gelen veri üyesi.  
  
 *Uzunluğu*  
 [in] Sütun uzunluğu için bağlanacak değişkeni.  
  
#### <a name="remarks"></a>Açıklamalar  
 Bkz: [COLUMN_NAME](../../data/oledb/column-name.md) COLUMN_NAME_ * makroları kullanıldığı hakkında bilgi.  

### <a name="column_name_ps_length_status"></a> COLUMN_NAME_PS_LENGTH_STATUS
Satır kümesi üzerindeki bir bağlamaya satır kümesindeki belirli bir sütunu temsil eder. Benzer şekilde [COLUMN_NAME](../../data/oledb/column-name.md)dışında bu makroyu duyarlığı, Ölçek, sütun uzunluğu ve sütununu durumunu alır.  
  
#### <a name="syntax"></a>Sözdizimi  
  
```cpp
COLUMN_NAME_PS_LENGTH_STATUS(pszName, nPrecision, nScale, data, length, status )  
```  
  
#### <a name="parameters"></a>Parametreler  
 *pszName*  
 [in] Sütun adı için bir işaretçi. Adı bir Unicode dize olması gerekir. Bu örneğin adının önüne bir 'L' koyarak gerçekleştirebilirsiniz: `L"MyColumn"`.  
  
 *nPrecision*  
 [in] Verilen duyarlık bağlamak istediğiniz sütun.  
  
 *nScale*  
 [in] Ölçeğin bağlamak istediğiniz sütun.  
  
 *Veri*  
 [in] Kullanıcı kaydındaki karşılık gelen veri üyesi.  
  
 *Uzunluğu*  
 [in] Sütun uzunluğu için bağlanacak değişkeni.  
  
 *Durumu*  
 [in] Sütun durumuna bağlı değişken.  
  
#### <a name="remarks"></a>Açıklamalar  
 Bkz: [COLUMN_NAME](../../data/oledb/column-name.md) COLUMN_NAME_ * makroları kullanıldığı hakkında bilgi.  

### <a name="column_name_ps_status"></a> COLUMN_NAME_PS_STATUS
Satır kümesi üzerindeki bir bağlamaya satır kümesindeki belirli bir sütunu temsil eder. Benzer şekilde [COLUMN_NAME](../../data/oledb/column-name.md)dışında bu makroyu kesinlik ve ölçek sütun durumunu da alır.  
  
#### <a name="syntax"></a>Sözdizimi  
  
```cpp
COLUMN_NAME_PS_STATUS(pszName, nPrecision, nScale, data, status )  
```  
  
#### <a name="parameters"></a>Parametreler  
 *pszName*  
 [in] Sütun adı için bir işaretçi. Adı bir Unicode dize olması gerekir. Bu örneğin adının önüne bir 'L' koyarak gerçekleştirebilirsiniz: `L"MyColumn"`.  
  
 *nPrecision*  
 [in] Verilen duyarlık bağlamak istediğiniz sütun.  
  
 *nScale*  
 [in] Ölçeğin bağlamak istediğiniz sütun.  
  
 *Veri*  
 [in] Kullanıcı kaydındaki karşılık gelen veri üyesi.  
  
 *Durumu*  
 [in] Sütun durumuna bağlı değişken.  
  
#### <a name="remarks"></a>Açıklamalar  
 Bkz: [COLUMN_NAME](../../data/oledb/column-name.md) COLUMN_NAME_ * makroları kullanıldığı hakkında bilgi.  

### <a name="column_name_status"></a> COLUMN_NAME_STATUS
Satır kümesi üzerindeki bir bağlamaya satır kümesindeki belirli bir sütunu temsil eder. Benzer şekilde [COLUMN_NAME](../../data/oledb/column-name.md)dışında bu makroyu sütununu durumunu da alır.  
  
#### <a name="syntax"></a>Sözdizimi  
  
```cpp
COLUMN_NAME_STATUS(pszName, data, status )  
```  
  
#### <a name="parameters"></a>Parametreler  
 *pszName*  
 [in] Sütun adı için bir işaretçi. Adı bir Unicode dize olması gerekir. Bu örneğin adının önüne bir 'L' koyarak gerçekleştirebilirsiniz: `L"MyColumn"`.  
  
 *Veri*  
 [in] Kullanıcı kaydındaki karşılık gelen veri üyesi.  
  
 *Durumu*  
 [in] Sütun durumuna bağlı değişken.  
  
#### <a name="remarks"></a>Açıklamalar  
 Bkz: [COLUMN_NAME](../../data/oledb/column-name.md) COLUMN_NAME_ * makroları kullanıldığı hakkında bilgi.  

### <a name="column_name_type"></a> COLUMN_NAME_TYPE
Satır kümesi üzerindeki bir bağlamaya satır kümesindeki belirli bir sütunu temsil eder. Benzer şekilde [COLUMN_NAME](../../data/oledb/column-name.md)dışında bu makroyu da veri türünü alır.  
  
#### <a name="syntax"></a>Sözdizimi  
  
```cpp
COLUMN_NAME_TYPE(pszName, wType, data)  
```  
  
#### <a name="parameters"></a>Parametreler  
 *pszName*  
 [in] Sütun adı için bir işaretçi. Adı bir Unicode dize olması gerekir. Bu örneğin adının önüne bir 'L' koyarak gerçekleştirebilirsiniz: `L"MyColumn"`.  
  
 *wType*  
 [in] Veri türü.  
  
 *Veri*  
 [in] Kullanıcı kaydındaki karşılık gelen veri üyesi.  
  
#### <a name="remarks"></a>Açıklamalar  
 Bkz: [COLUMN_NAME](../../data/oledb/column-name.md) COLUMN_NAME_ * makroları kullanıldığı hakkında bilgi.  

### <a name="column_name_type_ps"></a> COLUMN_NAME_TYPE_PS
Satır kümesi üzerindeki bir bağlamaya satır kümesindeki belirli bir sütunu temsil eder. Benzer şekilde [COLUMN_NAME](../../data/oledb/column-name.md)dışında bu makroyu veri türü, kesinlik ve ölçek alır.  
  
#### <a name="syntax"></a>Sözdizimi  
  
```cpp
COLUMN_NAME_TYPE_PS(pszName, wType, nPrecision, nScale, data)  
```  
  
#### <a name="parameters"></a>Parametreler  
 *pszName*  
 [in] Sütun adı için bir işaretçi. Adı bir Unicode dize olması gerekir. Bu örneğin adının önüne bir 'L' koyarak gerçekleştirebilirsiniz: `L"MyColumn"`.  
  
 *wType*  
 [in] Veri türü.  
  
 *nPrecision*  
 [in] Veri alma sırasında kullanılacak en fazla kesinlik ve *wType* olduğu `DBTYPE_NUMERIC`. Aksi takdirde, bu parametre yoksayılır.  
  
 *nScale*  
 [in] Veri alınırken kullanılacak ölçek ve *wType* olduğu `DBTYPE_NUMERIC` veya `DBTYPE_DECIMAL`.  
  
 *Veri*  
 [in] Kullanıcı kaydındaki karşılık gelen veri üyesi.  
  
#### <a name="remarks"></a>Açıklamalar  
 Bkz: [COLUMN_NAME](../../data/oledb/column-name.md) COLUMN_NAME_ * makroları kullanıldığı hakkında bilgi.  

### <a name="column_name_type_size"></a> COLUMN_NAME_TYPE_SIZE
Satır kümesi üzerindeki bir bağlamaya satır kümesindeki belirli bir sütunu temsil eder. Benzer şekilde [COLUMN_NAME](../../data/oledb/column-name.md)dışında bu makroyu veri türünü ve boyutunu alır.  
  
#### <a name="syntax"></a>Sözdizimi  
  
```cpp
COLUMN_NAME_TYPE_SIZE(pszName, wType, nLength, data)  
```  
  
#### <a name="parameters"></a>Parametreler  
 *pszName*  
 [in] Sütun adı için bir işaretçi. Adı bir Unicode dize olması gerekir. Bu örneğin adının önüne bir 'L' koyarak gerçekleştirebilirsiniz: `L"MyColumn"`.  
  
 *wType*  
 [in] Veri türü.  
  
 *nLength*  
 [in] Bayt cinsinden veri boyutu.  
  
 *Veri*  
 [in] Kullanıcı kaydındaki karşılık gelen veri üyesi.  
  
#### <a name="remarks"></a>Açıklamalar  
 Bkz: [COLUMN_NAME](../../data/oledb/column-name.md) COLUMN_NAME_ * makroları kullanıldığı hakkında bilgi.  

### <a name="column_name_type_status"></a> COLUMN_NAME_TYPE_STATUS
Satır kümesi üzerindeki bir bağlamaya satır kümesindeki belirli bir sütunu temsil eder. Benzer şekilde [COLUMN_NAME](../../data/oledb/column-name.md)dışında bu makroyu veri türü ve sütun durumunu da alır.  
  
#### <a name="syntax"></a>Sözdizimi  
  
```cpp
COLUMN_NAME_TYPE_STATUS(pszName, wType, status, data)  
```  
  
#### <a name="parameters"></a>Parametreler  
 *pszName*  
 [in] Sütun adı için bir işaretçi. Adı bir Unicode dize olması gerekir. Bu örneğin adının önüne bir 'L' koyarak gerçekleştirebilirsiniz: `L"MyColumn"`.  
  
 *wType*  
 [in] Veri türü.  
  
 *Durumu*  
 [in] Sütun durumuna bağlı değişken.  
  
 *Veri*  
 [in] Kullanıcı kaydındaki karşılık gelen veri üyesi.  
  
#### <a name="remarks"></a>Açıklamalar  
 Bkz: [COLUMN_NAME](../../data/oledb/column-name.md) COLUMN_NAME_ * makroları kullanıldığı hakkında bilgi.  

### <a name="end_column_map"></a> END_COLUMN_MAP
Sütun eşleme girişleri sonunu işaretler.  
  
#### <a name="syntax"></a>Sözdizimi  
  
```cpp
END_COLUMN_MAP()  
```  
  
#### <a name="remarks"></a>Açıklamalar  
 Bir satır kümesi üzerinde tek bir erişimcisi ile kullanılır. BEGIN_COLUMN_MAP makrosu END_COLUMN_MAP makrosu ile tamamlanır.  
  
#### <a name="example"></a>Örnek  
 Bkz: [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md).  

### <a name="define_command"></a> DEFINE_COMMAND
Satır kümesi kullanırken oluşturmak için kullanılacak komut belirtir [CCommand](../../data/oledb/ccommand-class.md) sınıfı. Yalnızca belirtilen uygulama türünü (ANSI veya Unicode) eşleşen dize türleri kabul eder.  
  
> [!NOTE]
>  Kullanmanız önerilir [defıne_command_ex](../../data/oledb/define-command-ex.md) DEFINE_COMMAND yerine.  
  
#### <a name="syntax"></a>Sözdizimi  
  
```cpp
DEFINE_COMMAND(x, szCommand)  
```  
  
#### <a name="parameters"></a>Parametreler  
 *x*  
 [in] Kullanıcı kayıt (komut) sınıfı adı.  
  
 *szCommand*  
 [in] Satır kümesi kullanırken oluşturmak için kullanılan komut dizesi [CCommand](../../data/oledb/ccommand-class.md).  
  
#### <a name="remarks"></a>Açıklamalar  
 Komut metni belirtmezseniz, varsayılan olarak, belirttiğiniz komut dizesi kullanılacak [CCommand::Open](../../data/oledb/ccommand-open.md) yöntemi.  
  
 Unicode olarak uygulamanızı varsa bu makroyu ANSI olarak uygulamanızı, ANSI dizelerini veya Unicode dizelerini kabul eder. Kullanmanız önerilir [defıne_command_ex](../../data/oledb/define-command-ex.md) DEFINE_COMMAND, yerine ANSI veya Unicode uygulama türünden bağımsız olarak, Unicode dizelerini önceki kabul ettiğinden.  
  
#### <a name="example"></a>Örnek  
 Bkz: [BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md).  

### <a name="define_command_ex"></a> DEFINE_COMMAND_EX
Satır kümesi kullanırken oluşturmak için kullanılacak komut belirtir [CCommand](../../data/oledb/ccommand-class.md) sınıfı. Unicode ve ANSI uygulamalarını destekler.  
  
#### <a name="syntax"></a>Sözdizimi  
  
```cpp
DEFINE_COMMAND_EX(x, wszCommand)  
```  
  
#### <a name="parameters"></a>Parametreler  
 *x*  
 [in] Kullanıcı kayıt (komut) sınıfı adı.  
  
 *wszCommand*  
 [in] Satır kümesi kullanırken oluşturmak için kullanılan komut dizesi [CCommand](../../data/oledb/ccommand-class.md).  
  
#### <a name="remarks"></a>Açıklamalar  
 Komut metni belirtmezseniz, varsayılan olarak, belirttiğiniz komut dizesi kullanılacak [CCommand::Open](../../data/oledb/ccommand-open.md) yöntemi.  
  
 Bu makro uygulama türünden bağımsız olarak, Unicode dizelerini kabul eder. Bu makro üzerinden tercih edilen [DEFINE_COMMAND](../../data/oledb/define-command.md) Unicode desteklediğinden, ANSI uygulamaların yanı sıra.  
  
#### <a name="example"></a>Örnek  
 Bkz: [BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md).  

### <a name="begin_param_map"></a> BEGIN_PARAM_MAP
Parametre eşleme girişleri başlangıcını işaretler.  
  
#### <a name="syntax"></a>Sözdizimi  
  
```cpp
BEGIN_PARAM_MAP(x)  
```  
  
#### <a name="parameters"></a>Parametreler  
 *x*  
 [in] Kullanıcı kayıt sınıfı adı.  
  
#### <a name="remarks"></a>Açıklamalar  
 Tarafından kullanılan parametreleri [komutları](https://msdn.microsoft.com/library/ms724608.aspx).  
  
#### <a name="example"></a>Örnek  
 Örneğin bakın [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) makrosu.  

### <a name="end_param_map"></a> END_PARAM_MAP
Parametre eşleme girişleri sonunu işaretler.  
  
#### <a name="syntax"></a>Sözdizimi  
  
```cpp
END_PARAM_MAP()  
```  
  
#### <a name="example"></a>Örnek  
 Örneğin bakın [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) makrosu.  
  
### <a name="set_param_type"></a> SET_PARAM_TYPE
SET_PARAM_TYPE makrosu giriş, çıkış veya giriş/çıkış izleyin COLUMN_ENTRY makroları belirtir.  
  
#### <a name="syntax"></a>Sözdizimi  
  
```cpp
SET_PARAM_TYPE(type)  
```  
  
#### <a name="parameters"></a>Parametreler  
 *Türü*  
 [in] İçin parametre türü.  
  
#### <a name="remarks"></a>Açıklamalar  
 Sağlayıcılar, temel alınan veri kaynağı tarafından desteklenen parametre giriş/çıkış türleri destekler. Bir veya daha fazla tür birleşimidir `DBPARAMIO` değerleri (bkz [IAccessor::CreateAccessor'ı yapıları](https://msdn.microsoft.com/library/ms716845.aspx) içinde *OLE DB Programcının Başvurusu*):  
  
-   `DBPARAMIO_NOTPARAM` Erişimci hiç parametre yok. Genellikle, ayarladığınız `eParamIO` şu değer satır Erişimcilerde parametreleri göz ardı edilir, kullanıcıyı şu aralıklarla uyar.  
  
-   `DBPARAMIO_INPUT` Giriş parametresi.  
  
-   `DBPARAMIO_OUTPUT` Çıkış parametresi.  
  
-   `DBPARAMIO_INPUT | DBPARAMIO_OUTPUT` , Hem giriş hem de çıkış parametresi parametredir.  
  
#### <a name="example"></a>Örnek  
```cpp  
class CArtistsProperty
{
public:
   short m_nReturn;
   short m_nAge;
   TCHAR m_szFirstName[21];
   TCHAR m_szLastName[31];

BEGIN_PARAM_MAP(CArtistsProperty)
   SET_PARAM_TYPE(DBPARAMIO_OUTPUT)
   COLUMN_ENTRY(1, m_nReturn)
   SET_PARAM_TYPE(DBPARAMIO_INPUT)
   COLUMN_ENTRY(2, m_nAge)
END_PARAM_MAP()

BEGIN_COLUMN_MAP(CArtistsProperty)
   COLUMN_ENTRY(1, m_szFirstName)
   COLUMN_ENTRY(2, m_szLastName)
END_COLUMN_MAP()

   HRESULT OpenDataSource()
   {
      CDataSource _db;
      _db.Open();
      return m_session.Open(_db);
   }

   void CloseDataSource()
   {
      m_session.Close();
   }

   CSession m_session;

   DEFINE_COMMAND_EX(CArtistsProperty, L" \
      { ? = SELECT Age FROM Artists WHERE Age < ? }")
};
``` 

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makrolar ve genel işlevler için OLE DB Tüketici Şablonları](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)    
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)    