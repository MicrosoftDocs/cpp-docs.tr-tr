---
description: 'Daha fazla bilgi edinin: CGopherFile sınıfı'
title: CGopherFile sınıfı
ms.date: 11/04/2016
f1_keywords:
- CGopherFile
- AFXINET/CGopherFile
- AFXINET/CGopherFile::CGopherFile
helpviewer_keywords:
- CGopherFile [MFC], CGopherFile
ms.assetid: 3ca9898f-8cdb-4495-bbde-46d40100feda
ms.openlocfilehash: 8f511bdaf3ae6417972ea19465c0392832a2b408
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184081"
---
# <a name="cgopherfile-class"></a>CGopherFile sınıfı

Bir gopher sunucusunda dosya bulma ve okuma işlevlerini sağlar.

> [!NOTE]
> Sınıflar `CGopherConnection` , `CGopherFile` , `CGopherFileFind` `CGopherLocator` ve üyeleri Windows XP platformunda çalışmadıklarından kullanım dışı bırakılmıştır, ancak önceki platformlarda çalışmaya devam ederler.

## <a name="syntax"></a>Syntax

```
class CGopherFile : public CInternetFile
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CGopherFile:: CGopherFile](#cgopherfile)|Bir `CGopherFile` nesnesi oluşturur.|

## <a name="remarks"></a>Açıklamalar

Gopher hizmeti, kullanıcıların bir Gopher dosyasına veri yazmasına izin vermez çünkü bu hizmet, bilgileri bulmak için temel olarak menü temelli bir arabirim olarak çalışır. `CGopherFile`Üye işlevleri `Write` , `WriteString` ve için uygulanmaz `Flush` `CGopherFile` . Bu işlevleri bir nesnesinde çağırmak `CGopherFile` , bir [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)döndürür.

Diğer MFC Internet sınıflarıyla nasıl çalıştığı hakkında daha fazla bilgi edinmek için `CGopherFile` bkz. [Winınet Ile Internet programlama](../../mfc/win32-internet-extensions-wininet.md)makalesi.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[CStdioFile](../../mfc/reference/cstdiofile-class.md)

[CInternetFile](../../mfc/reference/cinternetfile-class.md)

`CGopherFile`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFXINET. h

## <a name="cgopherfilecgopherfile"></a><a name="cgopherfile"></a> CGopherFile:: CGopherFile

Bu üye işlevi bir nesne oluşturmak için çağırılır `CGopherFile` .

```
CGopherFile(
    HINTERNET hFile,
    CGopherLocator& refLocator,
    CGopherConnection* pConnection);

CGopherFile(
    HINTERNET hFile,
    HINTERNET hSession,
    LPCTSTR pstrLocator,
    DWORD dwLocLen,
    DWORD_PTR dwContext);
```

### <a name="parameters"></a>Parametreler

*hFile*<br/>
Bir HıNTERNET dosyası tanıtıcısı.

*refLocator*<br/>
[CGopherLocator](../../mfc/reference/cgopherlocator-class.md) nesnesine bir başvuru.

*pConnection*<br/>
[CGopherConnection](../../mfc/reference/cgopherconnection-class.md) nesnesine yönelik bir işaretçi.

*hSession*<br/>
Geçerli Internet oturumuna yönelik bir tanıtıcı.

*pstrLocator*<br/>
Gopher sunucusunu bulmak için kullanılan dize işaretçisi. Gopher Konumlandırıcı hakkında daha fazla bilgi için bkz. [Gopher oturumları](cgopherlocator-class.md) .

*dwLocLen*<br/>
*PstrLocator* içindeki bayt sayısını IÇEREN bir DWORD.

*dwContext*<br/>
Açılan dosyanın bağlam tanımlayıcısına yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`CGopherFile`Gopher Internet oturumu sırasında bir dosyadan okumak için bir nesne gerekir.

Hiçbir şekilde doğrudan bir nesne oluşturmamanız gerekir `CGopherFile` . Bunun yerine, bir Gopher sunucusunda bir dosya açmak için [CGopherConnection:: OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile) çağırın.

## <a name="see-also"></a>Ayrıca bkz.

[CInternetFile sınıfı](../../mfc/reference/cinternetfile-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CInternetFile sınıfı](../../mfc/reference/cinternetfile-class.md)<br/>
[CGopherLocator sınıfı](../../mfc/reference/cgopherlocator-class.md)<br/>
[CGopherFileFind sınıfı](../../mfc/reference/cgopherfilefind-class.md)<br/>
[CGopherConnection sınıfı](../../mfc/reference/cgopherconnection-class.md)
