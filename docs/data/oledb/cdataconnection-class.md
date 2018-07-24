---
title: CDataConnection sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CDataConnection
- ATL.CDataConnection
- CDataConnection
- CDataConnection.CDataConnection
- ATL.CDataConnection.CDataConnection
- CDataConnection::CDataConnection
- ATL::CDataConnection::CDataConnection
- CDataConnection.Copy
- ATL.CDataConnection.Copy
- ATL::CDataConnection::Copy
- CDataConnection::Copy
- CDataConnection.Open
- ATL.CDataConnection.Open
- CDataConnection::Open
- ATL::CDataConnection::Open
- CDataConnection.OpenNewSession
- ATL.CDataConnection.OpenNewSession
- ATL::CDataConnection::OpenNewSession
- OpenNewSession
- CDataConnection::OpenNewSession
- CDataConnection::operatorBOOL
- ATL::CDataConnection::operatorBOOL
- CDataConnection.operatorBOOL
- ATL.CDataConnection.operatorBOOL
- CDataConnection::operatorBOOL
- ATL::CDataConnection::operatorBOOL
- CDataConnection.operatorBOOL
- ATL.CDataConnection.operatorBOOL
- CDataSource&
- CDataConnection.operatorCDataSource&
- operatorCDataSource&
- CDataConnection::operatorCDataSource&
- CDataSource*
- CDataConnection::operatorCDataSource*
- CDataConnection.operatorCDataSource*
- operatorCDataSource*
- CSession&
- CDataConnection::operatorCSession&
- CDataConnection.operatorCSession&
- operatorCSession&
- CDataConnection.operatorCSession*
- CDataConnection::operatorCSession*
- operatorCSession*
- CSession*
dev_langs:
- C++
helpviewer_keywords:
- CDataConnection class
- CDataConnection class, constructor
- Copy method
- Open method
- OpenNewSession method
- BOOL operator
- operator bool
- BOOL operator
- operator bool
- CDataSource& operator
- operator & (CDataSource)
- CDataSource* operator
- operator * (CDataSource)
- operator CSession&
- CSession& operator
- operator CSession*
- CSession* operator
ms.assetid: 77432d85-4e20-49ec-a0b0-142137828471
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: eafb9c3eb9c8d76ee0c714b6b7c7c2f4e9e7eef1
ms.sourcegitcommit: 7eadb968405bcb92ffa505e3ad8ac73483e59685
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/23/2018
ms.locfileid: "39207808"
---
# <a name="cdataconnection-class"></a>CDataConnection Sınıfı
Veri kaynağı ile bağlantı yönetir.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
class CDataConnection  
```  

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h 

## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[CDataConnection](#cdataconnection)|Oluşturucu. Oluşturur ve başlatır bir `CDataConnection` nesne.|  
|[kopyalama](#copy)|Mevcut bir veri bağlantısı bir kopyasını oluşturur.|  
|[açın](#open)|Başlatma dizesi kullanarak bir veri kaynağı bir bağlantı açar.|  
|[OpenNewSession](#opennewsession)|Geçerli bağlantı üzerinde yeni bir oturum açar.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[BOOL işleci](#op_bool)|Geçerli oturumu açık olup olmadığını belirler.|  
|[bool işleci](#op_bool_ole)|Geçerli oturumu açık olup olmadığını belirler.|  
|[işleç CDataSource &](#op_cdata_amp)|Kapsanan bir başvuru döndürür `CDataSource` nesne.|  
|[CDataSource * işleci](#op_cdata_star)|Kapsanan bir işaretçi döndürür `CDataSource` nesne.|  
|[işleç CSession &](#op_csession_amp)|Kapsanan bir başvuru döndürür `CSession` nesne.|  
|[işleç CSession *](#op_csession_star)|Kapsanan bir işaretçi döndürür `CSession` nesne.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CDataConnection` gerekli nesneleri (veri kaynağı ve oturum) ve bir veri kaynağına bağlanırken gerçekleştirmeniz gereken işinin bir kısmını kapsülleyen çünkü istemciler oluşturan için kullanışlı bir sınıftır  
  
 Olmadan `CDataConnection`, oluşturmak zorunda bir `CDataSource` nesne, çağrı kendi [OpenFromInitializationString](../../data/oledb/cdatasource-openfrominitializationstring.md) yöntemi, bir örneğini oluşturup bir [CSession](../../data/oledb/csession-class.md) nesne, arama, [ Açık](../../data/oledb/csession-open.md) yöntemi, oluşturup bir [CCommand](../../data/oledb/ccommand-class.md) nesne ve çağrı kendi `Open`* yöntemleri.  
  
 İle `CDataConnection`, yalnızca bir bağlantı nesnesi oluşturma, başlatma dizesi geçirin ve ardından komutları açmak için bu bağlantıyı kullanmak gerekir. Veritabanı bağlantınızı sürekli olarak kullanmayı planlıyorsanız, bu bağlantının açık kalması için iyi bir fikirdir ve `CDataConnection` bunu yapmanın kolay bir yol sağlar.  
  
> [!NOTE]
>  Birden çok oturumu işlemek için gereken bir veritabanı uygulaması oluşturuyorsanız, kullanmanız gerekecektir [OpenNewSession](../../data/oledb/cdataconnection-opennewsession.md).  

## <a name="#cdataconnection"></a> CDataConnection::CDataConnection
Oluşturur ve başlatır bir `CDataConnection` nesne.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
      CDataConnection();   

CDataConnection(const CDataConnection &ds);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *DS*  
 [in] Mevcut bir veri bağlantısı başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk geçersiz kılma yeni bir oluşturur `CDataConnection` varsayılan ayarlarla nesne.  
  
 İkinci geçersiz kılma yeni bir oluşturur `CDataConnection` ayarları, belirttiğiniz veri bağlantı nesnesi eşdeğer olan nesne. 

## <a name="#copy"></a> CDataConnection::Copy
Mevcut bir veri bağlantısı bir kopyasını oluşturur.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
      CDataConnection& Copy(const CDataConnection & ds) throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 *DS*  
 [in] Mevcut bir veri bağlantısı kopyalamak için bir başvuru. 

## <a name="#open"></a> CDataConnection::Open
Başlatma dizesi kullanarak bir veri kaynağı bir bağlantı açar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
HRESULT Open(LPCOLESTR szInitString) throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 *szInitString*  
 [in] Veri kaynağı için başlatma dizesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir HRESULT.  

## <a name="#opennewsession"></a> CDataConnection::OpenNewSession
Geçerli bağlantı nesnesinin veri kaynağı kullanarak yeni bir oturum açar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
HRESULT OpenNewSession(CSession & session) throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 *Oturumu*  
 [daraltma/genişletme] Yeni bir oturum nesnesi bir başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 Yeni bir oturum geçerli bağlantı nesnenin içerdiği veri kaynağı nesnesi kendi üst öğesi olarak kullanır ve tüm veri kaynağı olarak aynı bilgileri erişebilir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir HRESULT.  

## <a name="op_bool"></a> CDataConnection::operator BOOL
Geçerli oturumu açık olup olmadığını belirler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
operator BOOL() throw();  
  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Döndürür **BOOL** (MFC typedef) değeri. **DOĞRU** geçerli oturum açın; anlamına gelir **FALSE** geçerli oturum kapatıldığında anlamına gelir. 

## <a name="op_bool_ole"></a> CDataConnection::operator bool (OLE DB)
Geçerli oturumu açık olup olmadığını belirler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
operator bool() throw();  
  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Döndürür bir **bool** (C++ veri türü) değeri. **doğru** geçerli oturum açın; anlamına gelir **false** geçerli oturum kapatıldığında anlamına gelir.  

## <a name="op_cdata_amp"></a> CDataConnection::operator CDataSource&amp;
Kapsanan bir başvuru döndürür `CDataSource` nesne.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
operator const CDataSource&() throw();  
  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlecin bağımsız bir başvuru döndürür `CDataSource` geçirmenize izin nesnesi, bir `CDataConnection` nesne olduğu bir `CDataSource` başvurusu bekleniyor.  
  
### <a name="example"></a>Örnek  
 Bir işlev varsa (gibi `func` aşağıda) alan bir `CDataSource` kullanabileceğiniz başvuru `CDataSource&` geçirilecek bir `CDataConnection` bunun yerine nesne.  
  
 [!code-cpp[NVC_OLEDB_Consumer#3](../../data/oledb/codesnippet/cpp/cdataconnection-operator-cdatasource-amp_1.cpp)]  
  
 [!code-cpp[NVC_OLEDB_Consumer#4](../../data/oledb/codesnippet/cpp/cdataconnection-operator-cdatasource-amp_2.cpp)] 

## <a name="op_cdata_star"></a> CDataConnection::operator CDataSource *
Kapsanan bir işaretçi döndürür `CDataSource` nesne.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
operator const CDataSource*() throw();  
  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işleç içerdiği için bir işaretçi döndürür `CDataSource` geçirmenize izin nesnesi, bir `CDataConnection` nesne olduğu bir `CDataSource` işaretçi beklenmektedir.  
  
 Bkz: [işleci CDataSource &](../../data/oledb/cdataconnection-operator-cdatasource-amp.md) bir kullanım örneği için.  

## <a name="op_csession_amp"></a> CDataConnection::operator CSession&amp;
Kapsanan bir başvuru döndürür `CSession` nesne.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
operator const CSession&();  
  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlecin bağımsız bir başvuru döndürür `CSession` geçirmenize izin nesnesi, bir `CDataConnection` nesne olduğu bir `CSession` başvurusu bekleniyor.  
  
### <a name="example"></a>Örnek  
 Bir işlev varsa (gibi `func` aşağıda) alan bir `CSession` kullanabileceğiniz başvuru `CSession&` geçirilecek bir `CDataConnection` bunun yerine nesne.  
  
 [!code-cpp[NVC_OLEDB_Consumer#5](../../data/oledb/codesnippet/cpp/cdataconnection-operator-csession-amp_1.cpp)]  
  
 [!code-cpp[NVC_OLEDB_Consumer#6](../../data/oledb/codesnippet/cpp/cdataconnection-operator-csession-amp_2.cpp)]  

## <a name="op_csession_star"></a> CDataConnection::operator CSession *
Kapsanan bir işaretçi döndürür `CSession` nesne.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
operator const CSession*() throw();  
  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işleç içerdiği için bir işaretçi döndürür `CSession` geçirmenize izin nesnesi, bir `CDataConnection` nesne olduğu bir `CSession` işaretçi beklenmektedir.  
  
### <a name="example"></a>Örnek  
 Bkz: [işleç CSession &](../../data/oledb/cdataconnection-operator-csession-amp.md) bir kullanım örneği için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)