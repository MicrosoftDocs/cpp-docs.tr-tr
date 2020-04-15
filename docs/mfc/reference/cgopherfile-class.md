---
title: CGopherFile Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CGopherFile
- AFXINET/CGopherFile
- AFXINET/CGopherFile::CGopherFile
helpviewer_keywords:
- CGopherFile [MFC], CGopherFile
ms.assetid: 3ca9898f-8cdb-4495-bbde-46d40100feda
ms.openlocfilehash: e157a4509fe30b814a1834690a675906ac82afe7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373701"
---
# <a name="cgopherfile-class"></a>CGopherFile Sınıfı

Bir gopher sunucusunda dosyaları bulmak ve okumak için işlevsellik sağlar.

> [!NOTE]
> Sınıflar `CGopherConnection`, `CGopherFile` `CGopherFileFind`, `CGopherLocator` , , windows xp platformunda çalışmıyor çünkü onların üyeleri küçümsenmiş, ancak önceki platformlarda çalışmaya devam edecektir.

## <a name="syntax"></a>Sözdizimi

```
class CGopherFile : public CInternetFile
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CGopherFile::CGopherFile](#cgopherfile)|Bir `CGopherFile` nesne inşa eder.|

## <a name="remarks"></a>Açıklamalar

Bu hizmet esas olarak bilgi bulmak için menü tabanlı bir arabirim olarak çalıştığı için, gopher hizmeti kullanıcıların bir gopher dosyasına veri yazmasına izin vermez. Üye `CGopherFile` `Write`işlevler `WriteString`, `Flush` , , `CGopherFile`ve için uygulanmaz . Bu işlevleri bir `CGopherFile` nesne üzerinde çağıran, [cnotsupportedException](../../mfc/reference/cnotsupportedexception-class.md)döndürür.

Diğer MFC `CGopherFile` Internet sınıfları ile nasıl çalıştığı hakkında daha fazla bilgi edinmek için [WinInet ile internet programlama](../../mfc/win32-internet-extensions-wininet.md)makalesine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Cfile](../../mfc/reference/cfile-class.md)

[Cstdiofile](../../mfc/reference/cstdiofile-class.md)

[Cınternetfile](../../mfc/reference/cinternetfile-class.md)

`CGopherFile`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxinet.h

## <a name="cgopherfilecgopherfile"></a><a name="cgopherfile"></a>CGopherFile::CGopherFile

Bu üye işlev bir `CGopherFile` nesne oluşturmak için çağrılır.

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
HINTERNET dosyasının tutamacı.

*refLocator*<br/>
[CGopherLocator](../../mfc/reference/cgopherlocator-class.md) nesnesine bir gönderme.

*pBağlantı*<br/>
[CGopherConnection](../../mfc/reference/cgopherconnection-class.md) nesnesine işaretçi.

*hSession*<br/>
Geçerli Internet oturumunun tutamacı.

*pstrLocator*<br/>
Gopher sunucusunu bulmak için kullanılan bir dize işaretçisi. Gopher yer bulucuları hakkında daha fazla bilgi için [Gopher Sessions'a](cgopherlocator-class.md) bakın.

*dwLocLen*<br/>
*PstrLocator'daki*bayt sayısını içeren bir DWORD.

*dwBağlam*<br/>
Açılan dosyanın bağlam tanımlayıcısına işaretçi.

### <a name="remarks"></a>Açıklamalar

Bir gopher Internet oturumu sırasında bir dosyadan okumak için bir `CGopherFile` nesne gerekir.

Hiçbir `CGopherFile` nesneyi doğrudan oluşturmazsınız. Bunun yerine, [cgopherConnection'ı arayın::Bir](../../mfc/reference/cgopherconnection-class.md#openfile) gopher sunucusunda dosya açmak için OpenFile'ı arayın.

## <a name="see-also"></a>Ayrıca bkz.

[CInternetFile Sınıfı](../../mfc/reference/cinternetfile-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CInternetFile Sınıfı](../../mfc/reference/cinternetfile-class.md)<br/>
[CGopherLocator Sınıf](../../mfc/reference/cgopherlocator-class.md)<br/>
[CGopherFileFind Sınıf](../../mfc/reference/cgopherfilefind-class.md)<br/>
[CGopherConnection Sınıfı](../../mfc/reference/cgopherconnection-class.md)
