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
ms.openlocfilehash: fe954e218a099fa7956748904a4baa89f741c52f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368610"
---
# <a name="cdataconnection-class"></a>CDataConnection Sınıfı

Veri kaynağıyla bağlantıyı yönetir.

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
|[CDataConnection](#cdataconnection)|Oluşturucu. Bir `CDataConnection` nesneyi anında laştırır ve başharfe alar.|
|[Kopyala](#copy)|Varolan bir veri bağlantısının kopyasını oluşturur.|
|[Aç](#open)|Bir başlatma dizesini kullanarak bir veri kaynağına bağlantı açar.|
|[OpenNewSession](#opennewsession)|Geçerli bağlantıda yeni bir oturum açar.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[operatör BOOL](#op_bool)|Geçerli oturumun açık olup olmadığını belirler.|
|[operatör bool](#op_bool_ole)|Geçerli oturumun açık olup olmadığını belirler.|
|[operatör CDataSource&](#op_cdata_amp)|İçe yer alan `CDataSource` nesneye bir başvuru verir.|
|[operatör CDataSource*](#op_cdata_star)|Bir işaretçiyi `CDataSource` içerdiği nesneye döndürür.|
|[operatör CSession&](#op_csession_amp)|İçe yer alan `CSession` nesneye bir başvuru verir.|
|[operatör CSession*](#op_csession_star)|Bir işaretçiyi `CSession` içerdiği nesneye döndürür.|

## <a name="remarks"></a>Açıklamalar

`CDataConnection`gerekli nesneleri (veri kaynağı ve oturum) ve bir veri kaynağına bağlanırken yapmanız gereken bazı işleri kapsüllediği için istemci oluşturmak için yararlı bir sınıftır

Olmadan `CDataConnection`, `CDataSource` bir nesne oluşturmak zorunda, [openFromInitializationString](../../data/oledb/cdatasource-openfrominitializationstring.md) yöntemini aramak, sonra bir [CSession](../../data/oledb/csession-class.md) nesnesinin bir örneği oluşturmak, `Open`onun [Açık](../../data/oledb/csession-open.md) yöntemini aramak, sonra bir [CCommand](../../data/oledb/ccommand-class.md) nesnesi oluşturmak ve onun * yöntemleri ni çağırmak.

Ile `CDataConnection`, sadece bir bağlantı nesnesi oluşturmak için, bir başlatma dize geçmek ve sonra komutları açmak için bu bağlantıyı kullanın. Veritabanına olan bağlantınızı tekrar tekrar kullanmayı planlıyorsanız, bağlantıyı açık tutmak iyi `CDataConnection` bir fikirdir ve bunu yapmak için kullanışlı bir yol sağlar.

> [!NOTE]
> Birden çok oturumu işlemesi gereken bir veritabanı uygulaması oluşturuyorsanız, [OpenNewSession'ı](../../data/oledb/cdataconnection-opennewsession.md)kullanmanız gerekir.

## <a name="cdataconnectioncdataconnection"></a><a name="cdataconnection"></a>CDataConnection::CDataConnection

Bir `CDataConnection` nesneyi anında laştırır ve başharfe alar.

### <a name="syntax"></a>Sözdizimi

```cpp
CDataConnection();
CDataConnection(const CDataConnection &ds);
```

#### <a name="parameters"></a>Parametreler

*Ds*<br/>
[içinde] Varolan bir veri bağlantısına başvuru.

### <a name="remarks"></a>Açıklamalar

İlk geçersiz kılma varsayılan `CDataConnection` ayarları olan yeni bir nesne oluşturur.

İkinci geçersiz kılma, belirttiğiniz veri bağlantısı nesnesine eşdeğer ayarlara sahip yeni `CDataConnection` bir nesne oluşturur.

## <a name="cdataconnectioncopy"></a><a name="copy"></a>CDataConnection::Kopyala

Varolan bir veri bağlantısının kopyasını oluşturur.

### <a name="syntax"></a>Sözdizimi

```cpp
CDataConnection& Copy(const CDataConnection & ds) throw();
```

#### <a name="parameters"></a>Parametreler

*Ds*<br/>
[içinde] Kopyalamak için varolan bir veri bağlantısına başvuru.

## <a name="cdataconnectionopen"></a><a name="open"></a>CDataConnection::Aç

Bir başlatma dizesini kullanarak bir veri kaynağına bağlantı açar.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT Open(LPCOLESTR szInitString) throw();
```

#### <a name="parameters"></a>Parametreler

*szInitString*<br/>
[içinde] Veri kaynağı için başlatma dizesi.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT.

## <a name="cdataconnectionopennewsession"></a><a name="opennewsession"></a>CDataConnection::OpenNewSession

Geçerli bağlantı nesnesinin veri kaynağını kullanarak yeni bir oturum açar.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT OpenNewSession(CSession & session) throw();
```

#### <a name="parameters"></a>Parametreler

*Oturum*<br/>
[içeri/çıkış] Yeni oturum nesnesine bir başvuru.

### <a name="remarks"></a>Açıklamalar

Yeni oturum, geçerli bağlantı nesnesinin içerdiği veri kaynağı nesnesini üst öğesi olarak kullanır ve veri kaynağıyla aynı bilgilerin tümüne erişebilir.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT.

## <a name="cdataconnectionoperator-bool"></a><a name="op_bool"></a>CDataConnection::operatör BOOL

Geçerli oturumun açık olup olmadığını belirler.

### <a name="syntax"></a>Sözdizimi

```cpp
operator BOOL() throw();
```

### <a name="remarks"></a>Açıklamalar

**BOOL** (MFC typedef) değerini verir. **TRUE,** geçerli oturumun açık olduğu anlamına gelir; **FALSE,** geçerli oturumun kapalı olduğu anlamına gelir.

## <a name="cdataconnectionoperator-bool-ole-db"></a><a name="op_bool_ole"></a>CDataConnection::operatör bool (OLE DB)

Geçerli oturumun açık olup olmadığını belirler.

### <a name="syntax"></a>Sözdizimi

```cpp
operator bool() throw();
```

### <a name="remarks"></a>Açıklamalar

**Bool** (C++ veri türü) değerini döndürür. **geçerli** oturumun açık olduğu anlamına gelir; **false,** geçerli oturumun kapalı olduğu anlamına gelir.

## <a name="cdataconnectionoperator-cdatasourceamp"></a><a name="op_cdata_amp"></a>CDataConnection::operatör CDataSource&amp;

İçe yer alan `CDataSource` nesneye bir başvuru verir.

### <a name="syntax"></a>Sözdizimi

```cpp
operator const CDataSource&() throw();
```

### <a name="remarks"></a>Açıklamalar

Bu işleç, bir `CDataSource` `CDataConnection` `CDataSource` başvuru beklenen bir nesneyi geçirmenize olanak tanıyan, içerdiği nesneye bir başvuru döndürür.

### <a name="example"></a>Örnek

`func` Referans alan bir `CDataSource` işleviniz (aşağıdaki gibi) varsa, `CDataSource&` bunun yerine `CDataConnection` bir nesneyi geçmek için kullanabilirsiniz.

[!code-cpp[NVC_OLEDB_Consumer#3](../../data/oledb/codesnippet/cpp/cdataconnection-operator-cdatasource-amp_1.cpp)]

[!code-cpp[NVC_OLEDB_Consumer#4](../../data/oledb/codesnippet/cpp/cdataconnection-operator-cdatasource-amp_2.cpp)]

## <a name="cdataconnectionoperator-cdatasource"></a><a name="op_cdata_star"></a>CDataConnection::operatör CDataSource*

Bir işaretçiyi `CDataSource` içerdiği nesneye döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
operator const CDataSource*() throw();
```

### <a name="remarks"></a>Açıklamalar

Bu işleç, `CDataSource` `CDataConnection` `CDataSource` işaretçi beklenen bir nesneyi geçmenize olanak tanıyan bir işaretçiyi içerdiği nesneye döndürür.

Kullanım örneği için [operatör CDataSource&](../../data/oledb/cdataconnection-operator-cdatasource-amp.md) bakın.

## <a name="cdataconnectionoperator-csessionamp"></a><a name="op_csession_amp"></a>CDataConnection::operatör CSession&amp;

İçe yer alan `CSession` nesneye bir başvuru verir.

### <a name="syntax"></a>Sözdizimi

```cpp
operator const CSession&();
```

### <a name="remarks"></a>Açıklamalar

Bu işleç, bir `CSession` `CDataConnection` `CSession` başvuru beklenen bir nesneyi geçirmenize olanak tanıyan, içerdiği nesneye bir başvuru döndürür.

### <a name="example"></a>Örnek

`func` Referans alan bir `CSession` işleviniz (aşağıdaki gibi) varsa, `CSession&` bunun yerine `CDataConnection` bir nesneyi geçmek için kullanabilirsiniz.

[!code-cpp[NVC_OLEDB_Consumer#5](../../data/oledb/codesnippet/cpp/cdataconnection-operator-csession-amp_1.cpp)]

[!code-cpp[NVC_OLEDB_Consumer#6](../../data/oledb/codesnippet/cpp/cdataconnection-operator-csession-amp_2.cpp)]

## <a name="cdataconnectionoperator-csession"></a><a name="op_csession_star"></a>CDataConnection::operatör CSession*

Bir işaretçiyi `CSession` içerdiği nesneye döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
operator const CSession*() throw();
```

### <a name="remarks"></a>Açıklamalar

Bu işleç, `CSession` `CDataConnection` `CSession` işaretçi beklenen bir nesneyi geçmenize olanak tanıyan bir işaretçiyi içerdiği nesneye döndürür.

### <a name="example"></a>Örnek

Kullanım örneği için [operatör CSession&](../../data/oledb/cdataconnection-operator-csession-amp.md) bakın.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)
