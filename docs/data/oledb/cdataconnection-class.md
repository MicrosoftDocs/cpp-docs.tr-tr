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
ms.openlocfilehash: e966ce8d0f8b277c0edde2b0b9b345a11c6a964c
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79442494"
---
# <a name="cdataconnection-class"></a>CDataConnection Sınıfı

Veri kaynağıyla bağlantıyı yönetir.

## <a name="syntax"></a>Sözdizimi

```cpp
class CDataConnection
```

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atldbclı. h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[CDataConnection](#cdataconnection)|Oluşturucu. `CDataConnection` nesnesini başlatır ve başlatır.|
|[Kopyala](#copy)|Varolan bir veri bağlantısının kopyasını oluşturur.|
|[Açın](#open)|Başlatma dizesi kullanarak bir veri kaynağına bir bağlantı açar.|
|[OpenNewSession](#opennewsession)|Geçerli bağlantıda yeni bir oturum açar.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[işleç BOOL](#op_bool)|Geçerli oturumun açık olup olmadığını belirler.|
|[işleç bool](#op_bool_ole)|Geçerli oturumun açık olup olmadığını belirler.|
|[CDataSource işleci &](#op_cdata_amp)|İçerilen `CDataSource` nesnesine bir başvuru döndürür.|
|[CDataSource * işleci](#op_cdata_star)|İçerilen `CDataSource` nesnesine bir işaretçi döndürür.|
|[işleç CSession &](#op_csession_amp)|İçerilen `CSession` nesnesine bir başvuru döndürür.|
|[CSession * işleci](#op_csession_star)|İçerilen `CSession` nesnesine bir işaretçi döndürür.|

## <a name="remarks"></a>Açıklamalar

`CDataConnection`, gerekli nesneleri (veri kaynağı ve oturumu) ve bir veri kaynağına bağlanırken yapmanız gereken bazı işleri (veri kaynağı ve oturum) sarmalayan istemciler oluşturmak için faydalı bir sınıftır

`CDataConnection`olmadan bir `CDataSource` nesnesi oluşturmanız, [Openfrominitializationstring](../../data/oledb/cdatasource-openfrominitializationstring.md) metodunu çağırmanız, sonra bir [CSession](../../data/oledb/csession-class.md) nesnesi örneği oluşturmanız, [Open](../../data/oledb/csession-open.md) metodunu çağırmanız, sonra bir [CCommand](../../data/oledb/ccommand-class.md) nesnesi oluşturmanız ve `Open`* yöntemlerini çağırmanız gerekir.

`CDataConnection`ile yalnızca bir bağlantı nesnesi oluşturmanız, bir başlatma dizesi iletmeniz ve ardından bu bağlantıyı kullanarak komutları açmanız gerekir. Veritabanı bağlantınızı sürekli olarak kullanmayı planlıyorsanız, bağlantının açık tutulması iyi bir fikirdir ve `CDataConnection` bunu yapmak için kullanışlı bir yol sağlar.

> [!NOTE]
>  Birden çok oturumu işlemesi gereken bir veritabanı uygulaması oluşturuyorsanız, [OpenNewSession](../../data/oledb/cdataconnection-opennewsession.md)kullanmanız gerekir.

## <a name="cdataconnection"></a>CDataConnection:: CDataConnection

`CDataConnection` nesnesini başlatır ve başlatır.

### <a name="syntax"></a>Sözdizimi

```cpp
CDataConnection();
CDataConnection(const CDataConnection &ds);
```

#### <a name="parameters"></a>Parametreler

*FID*<br/>
'ndaki Mevcut bir veri bağlantısına başvuru.

### <a name="remarks"></a>Açıklamalar

İlk geçersiz kılma varsayılan ayarlarla yeni bir `CDataConnection` nesnesi oluşturur.

İkinci geçersiz kılma, belirttiğiniz veri bağlantısı nesnesine denk ayarlarla yeni bir `CDataConnection` nesnesi oluşturur.

## <a name="copy"></a>CDataConnection:: Copy

Varolan bir veri bağlantısının kopyasını oluşturur.

### <a name="syntax"></a>Sözdizimi

```cpp
CDataConnection& Copy(const CDataConnection & ds) throw();
```

#### <a name="parameters"></a>Parametreler

*FID*<br/>
'ndaki Kopyalamak için mevcut bir veri bağlantısına bir başvuru.

## <a name="open"></a>CDataConnection:: Open

Başlatma dizesi kullanarak bir veri kaynağına bir bağlantı açar.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT Open(LPCOLESTR szInitString) throw();
```

#### <a name="parameters"></a>Parametreler

*Szınitstring*<br/>
'ndaki Veri kaynağı için başlatma dizesi.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

## <a name="opennewsession"></a>CDataConnection:: OpenNewSession

Geçerli bağlantı nesnesinin veri kaynağını kullanarak yeni bir oturum açar.

### <a name="syntax"></a>Sözdizimi

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

## <a name="op_bool"></a>CDataConnection:: operator BOOL

Geçerli oturumun açık olup olmadığını belirler.

### <a name="syntax"></a>Sözdizimi

```cpp
operator BOOL() throw();
```

### <a name="remarks"></a>Açıklamalar

**Bool** (MFC typedef) değerini döndürür. **Doğru** , geçerli oturumun açık olduğu anlamına gelir; **Yanlış** , geçerli oturumun kapalı olduğu anlamına gelir.

## <a name="op_bool_ole"></a>CDataConnection:: operator bool (OLE DB)

Geçerli oturumun açık olup olmadığını belirler.

### <a name="syntax"></a>Sözdizimi

```cpp
operator bool() throw();
```

### <a name="remarks"></a>Açıklamalar

Bir **bool** (C++ veri türü) değeri döndürür. **doğru** , geçerli oturumun açık olduğu anlamına gelir; **yanlış** , geçerli oturumun kapalı olduğu anlamına gelir.

## <a name="op_cdata_amp"></a>CDataConnection:: operator CDataSource&amp;

İçerilen `CDataSource` nesnesine bir başvuru döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
operator const CDataSource&() throw();
```

### <a name="remarks"></a>Açıklamalar

Bu işleç, içerilen `CDataSource` nesnesine bir başvuru döndürür ve bir `CDataSource` başvurusunun beklenildiği bir `CDataConnection` nesnesini geçirmenize olanak sağlar.

### <a name="example"></a>Örnek

`CDataSource` başvuru alan bir işleviniz varsa (aşağıdaki `func` gibi), bunun yerine `CDataConnection` nesnesini geçirmek için `CDataSource&` kullanabilirsiniz.

[!code-cpp[NVC_OLEDB_Consumer#3](../../data/oledb/codesnippet/cpp/cdataconnection-operator-cdatasource-amp_1.cpp)]

[!code-cpp[NVC_OLEDB_Consumer#4](../../data/oledb/codesnippet/cpp/cdataconnection-operator-cdatasource-amp_2.cpp)]

## <a name="op_cdata_star"></a>CDataConnection:: operator CDataSource *

İçerilen `CDataSource` nesnesine bir işaretçi döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
operator const CDataSource*() throw();
```

### <a name="remarks"></a>Açıklamalar

Bu işleç, içerilen `CDataSource` nesnesine bir işaretçi döndürür ve bir `CDataSource` işaretçisinin beklenildiği bir `CDataConnection` nesnesini geçirmenize olanak sağlar.

Kullanım örneği için bkz. [CDataSource & işleci](../../data/oledb/cdataconnection-operator-cdatasource-amp.md) .

## <a name="op_csession_amp"></a>CDataConnection:: operator CSession&amp;

İçerilen `CSession` nesnesine bir başvuru döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
operator const CSession&();
```

### <a name="remarks"></a>Açıklamalar

Bu işleç, içerilen `CSession` nesnesine bir başvuru döndürür ve bir `CSession` başvurusunun beklenildiği bir `CDataConnection` nesnesini geçirmenize olanak sağlar.

### <a name="example"></a>Örnek

`CSession` başvuru alan bir işleviniz varsa (aşağıdaki `func` gibi), bunun yerine `CDataConnection` nesnesini geçirmek için `CSession&` kullanabilirsiniz.

[!code-cpp[NVC_OLEDB_Consumer#5](../../data/oledb/codesnippet/cpp/cdataconnection-operator-csession-amp_1.cpp)]

[!code-cpp[NVC_OLEDB_Consumer#6](../../data/oledb/codesnippet/cpp/cdataconnection-operator-csession-amp_2.cpp)]

## <a name="op_csession_star"></a>CDataConnection:: operator CSession *

İçerilen `CSession` nesnesine bir işaretçi döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
operator const CSession*() throw();
```

### <a name="remarks"></a>Açıklamalar

Bu işleç, içerilen `CSession` nesnesine bir işaretçi döndürür ve bir `CSession` işaretçisinin beklenildiği bir `CDataConnection` nesnesini geçirmenize olanak sağlar.

### <a name="example"></a>Örnek

Kullanım örneği için bkz. [operator CSession &](../../data/oledb/cdataconnection-operator-csession-amp.md) .

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)