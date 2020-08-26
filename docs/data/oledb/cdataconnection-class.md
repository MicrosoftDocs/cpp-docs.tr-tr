---
title: CDataConnection Sınıfı
ms.date: 03/27/2019
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
ms.openlocfilehash: 118b8d09b90899eca0f257e319aabbefd92f359f
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88838406"
---
# <a name="cdataconnection-class"></a>CDataConnection Sınıfı

Veri kaynağıyla bağlantıyı yönetir.

## <a name="syntax"></a>Syntax

```cpp
class CDataConnection
```

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atldbclı. h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

| Ad | Açıklama |
|-|-|
|[CDataConnection](#cdataconnection)|Oluşturucu. Bir nesneyi örnekleyen ve başlatır `CDataConnection` .|
|[Kopyala](#copy)|Varolan bir veri bağlantısının kopyasını oluşturur.|
|[Aç](#open)|Başlatma dizesi kullanarak bir veri kaynağına bir bağlantı açar.|
|[OpenNewSession](#opennewsession)|Geçerli bağlantıda yeni bir oturum açar.|

### <a name="operators"></a>İşleçler

| Ad | Açıklama |
|-|-|
|[işleç BOOL](#op_bool)|Geçerli oturumun açık olup olmadığını belirler.|
|[işleç bool](#op_bool_ole)|Geçerli oturumun açık olup olmadığını belirler.|
|[CDataSource işleci&](#op_cdata_amp)|İçerilen nesneye bir başvuru döndürür `CDataSource` .|
|[CDataSource * işleci](#op_cdata_star)|İçerilen nesneye bir işaretçi döndürür `CDataSource` .|
|[işleç CSession&](#op_csession_amp)|İçerilen nesneye bir başvuru döndürür `CSession` .|
|[CSession * işleci](#op_csession_star)|İçerilen nesneye bir işaretçi döndürür `CSession` .|

## <a name="remarks"></a>Açıklamalar

`CDataConnection` , gerekli nesneleri (veri kaynağı ve oturumu) ve bir veri kaynağına bağlanırken yapmanız gereken bazı işleri (veri kaynağı ve oturum) sarmalayan ve istemci oluşturmaya yönelik yararlı bir sınıftır

Olmadan `CDataConnection` bir `CDataSource` nesnesi oluşturmanız, [Openfrominitializationstring](../../data/oledb/cdatasource-openfrominitializationstring.md) metodunu çağırmanız, sonra bir [CSession](../../data/oledb/csession-class.md) nesnesi örneği oluşturmanız, [Open](../../data/oledb/csession-open.md) metodunu çağırmanız ve sonra bir [CCommand](../../data/oledb/ccommand-class.md) nesnesi oluşturmanız ve `Open` * yöntemlerini çağırmanız gerekir.

İle `CDataConnection` yalnızca bir bağlantı nesnesi oluşturmanız, bir başlatma dizesi iletmeniz ve ardından bu bağlantıyı kullanarak komutları açmanız gerekir. Veritabanı bağlantınızı sürekli olarak kullanmayı planlıyorsanız, bağlantının açık tutulması iyi bir fikirdir ve `CDataConnection` bunu yapmak için kullanışlı bir yol sağlar.

> [!NOTE]
> Birden çok oturumu işlemesi gereken bir veritabanı uygulaması oluşturuyorsanız, [OpenNewSession](../../data/oledb/cdataconnection-opennewsession.md)kullanmanız gerekir.

## <a name="cdataconnectioncdataconnection"></a><a name="cdataconnection"></a> CDataConnection:: CDataConnection

Bir nesneyi örnekleyen ve başlatır `CDataConnection` .

### <a name="syntax"></a>Söz dizimi

```cpp
CDataConnection();
CDataConnection(const CDataConnection &ds);
```

#### <a name="parameters"></a>Parametreler

*FID*<br/>
'ndaki Mevcut bir veri bağlantısına başvuru.

### <a name="remarks"></a>Açıklamalar

İlk geçersiz kılma `CDataConnection` varsayılan ayarlarla yeni bir nesne oluşturur.

İkinci geçersiz kılma, `CDataConnection` belirttiğiniz veri bağlantısı nesnesine denk ayarların bulunduğu yeni bir nesne oluşturur.

## <a name="cdataconnectioncopy"></a><a name="copy"></a> CDataConnection:: Copy

Varolan bir veri bağlantısının kopyasını oluşturur.

### <a name="syntax"></a>Söz dizimi

```cpp
CDataConnection& Copy(const CDataConnection & ds) throw();
```

#### <a name="parameters"></a>Parametreler

*FID*<br/>
'ndaki Kopyalamak için mevcut bir veri bağlantısına bir başvuru.

## <a name="cdataconnectionopen"></a><a name="open"></a> CDataConnection:: Open

Başlatma dizesi kullanarak bir veri kaynağına bir bağlantı açar.

### <a name="syntax"></a>Söz dizimi

```cpp
HRESULT Open(LPCOLESTR szInitString) throw();
```

#### <a name="parameters"></a>Parametreler

*Szınitstring*<br/>
'ndaki Veri kaynağı için başlatma dizesi.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

## <a name="cdataconnectionopennewsession"></a><a name="opennewsession"></a> CDataConnection:: OpenNewSession

Geçerli bağlantı nesnesinin veri kaynağını kullanarak yeni bir oturum açar.

### <a name="syntax"></a>Söz dizimi

```cpp
HRESULT OpenNewSession(CSession & session) throw();
```

#### <a name="parameters"></a>Parametreler

*oturumuna*<br/>
[ın/out] Yeni oturum nesnesine bir başvuru.

### <a name="remarks"></a>Açıklamalar

Yeni oturum, geçerli bağlantı nesnesinin üst öğesi olarak bulunan veri kaynağı nesnesini kullanır ve veri kaynağıyla aynı bilgilere erişebilir.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

## <a name="cdataconnectionoperator-bool"></a><a name="op_bool"></a> CDataConnection:: operator BOOL

Geçerli oturumun açık olup olmadığını belirler.

### <a name="syntax"></a>Syntax

```cpp
operator BOOL() throw();
```

### <a name="remarks"></a>Açıklamalar

**Bool** (MFC typedef) değerini döndürür. **Doğru** , geçerli oturumun açık olduğu anlamına gelir; **Yanlış** , geçerli oturumun kapalı olduğu anlamına gelir.

## <a name="cdataconnectionoperator-bool-ole-db"></a><a name="op_bool_ole"></a> CDataConnection:: operator bool (OLE DB)

Geçerli oturumun açık olup olmadığını belirler.

### <a name="syntax"></a>Syntax

```cpp
operator bool() throw();
```

### <a name="remarks"></a>Açıklamalar

Bir **`bool`** (C++ veri türü) değeri döndürür. **`true`** Geçerli oturumun açık olduğu anlamına gelir; **`false`** geçerli oturumun kapalı olduğu anlamına gelir.

## <a name="cdataconnectionoperator-cdatasourceamp"></a><a name="op_cdata_amp"></a> CDataConnection:: operator CDataSource&amp;

İçerilen nesneye bir başvuru döndürür `CDataSource` .

### <a name="syntax"></a>Syntax

```cpp
operator const CDataSource&() throw();
```

### <a name="remarks"></a>Açıklamalar

Bu işleç, içerilen nesneye bir başvuru döndürür `CDataSource` , bu da bir `CDataConnection` başvurunun beklenildiği bir nesneyi geçirmenize olanak sağlar `CDataSource` .

### <a name="example"></a>Örnek

Başvuru alan bir işleviniz varsa ( `func` aşağıdaki gibi) `CDataSource` , `CDataSource&` bunun yerine bir nesneyi geçirmek için kullanabilirsiniz `CDataConnection` .

[!code-cpp[NVC_OLEDB_Consumer#3](../../data/oledb/codesnippet/cpp/cdataconnection-operator-cdatasource-amp_1.cpp)]

[!code-cpp[NVC_OLEDB_Consumer#4](../../data/oledb/codesnippet/cpp/cdataconnection-operator-cdatasource-amp_2.cpp)]

## <a name="cdataconnectionoperator-cdatasource"></a><a name="op_cdata_star"></a> CDataConnection:: operator CDataSource *

İçerilen nesneye bir işaretçi döndürür `CDataSource` .

### <a name="syntax"></a>Syntax

```cpp
operator const CDataSource*() throw();
```

### <a name="remarks"></a>Açıklamalar

Bu işleç, içerilen nesneye bir işaretçi döndürür `CDataSource` , bu da bir `CDataConnection` işaretçinin beklenildiği bir nesneyi geçirmenize olanak sağlar `CDataSource` .

Kullanım örneği için bkz. [CDataSource&işleci ](../../data/oledb/cdataconnection-operator-cdatasource-amp.md) .

## <a name="cdataconnectionoperator-csessionamp"></a><a name="op_csession_amp"></a> CDataConnection:: operator CSession&amp;

İçerilen nesneye bir başvuru döndürür `CSession` .

### <a name="syntax"></a>Syntax

```cpp
operator const CSession&();
```

### <a name="remarks"></a>Açıklamalar

Bu işleç, içerilen nesneye bir başvuru döndürür `CSession` , bu da bir `CDataConnection` başvurunun beklenildiği bir nesneyi geçirmenize olanak sağlar `CSession` .

### <a name="example"></a>Örnek

Başvuru alan bir işleviniz varsa ( `func` aşağıdaki gibi) `CSession` , `CSession&` bunun yerine bir nesneyi geçirmek için kullanabilirsiniz `CDataConnection` .

[!code-cpp[NVC_OLEDB_Consumer#5](../../data/oledb/codesnippet/cpp/cdataconnection-operator-csession-amp_1.cpp)]

[!code-cpp[NVC_OLEDB_Consumer#6](../../data/oledb/codesnippet/cpp/cdataconnection-operator-csession-amp_2.cpp)]

## <a name="cdataconnectionoperator-csession"></a><a name="op_csession_star"></a> CDataConnection:: operator CSession *

İçerilen nesneye bir işaretçi döndürür `CSession` .

### <a name="syntax"></a>Syntax

```cpp
operator const CSession*() throw();
```

### <a name="remarks"></a>Açıklamalar

Bu işleç, içerilen nesneye bir işaretçi döndürür `CSession` , bu da bir `CDataConnection` işaretçinin beklenildiği bir nesneyi geçirmenize olanak sağlar `CSession` .

### <a name="example"></a>Örnek

Kullanım örneği için bkz. [operator CSession&](../../data/oledb/cdataconnection-operator-csession-amp.md) .

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB tüketici şablonları başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)
