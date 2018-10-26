---
title: CGopherFile sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CGopherFile
- AFXINET/CGopherFile
- AFXINET/CGopherFile::CGopherFile
dev_langs:
- C++
helpviewer_keywords:
- CGopherFile [MFC], CGopherFile
ms.assetid: 3ca9898f-8cdb-4495-bbde-46d40100feda
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 083ed824ce8586295e398d32ed14e17f8d334358
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50080955"
---
# <a name="cgopherfile-class"></a>CGopherFile sınıfı

Bulmak ve bir gopher sunucusunda dosyaları okumak için gereken işlevleri sağlar.

> [!NOTE]
>  Sınıfları `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` ve üyeleri bırakılmıştır, Windows XP platformu üzerinde çalışmaz, ancak önceki platformları üzerinde çalışmaya devam eder.

## <a name="syntax"></a>Sözdizimi

```
class CGopherFile : public CInternetFile
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CGopherFile::CGopherFile](#cgopherfile)|Oluşturur bir `CGopherFile` nesne.|

## <a name="remarks"></a>Açıklamalar

Gopher hizmet bu hizmeti bilgileri bulmak için çoğunlukla bir menü yönlendirmeli arabirimi gördüğünden bir gopher dosyaya veri yazmak kullanıcılar izin vermez. `CGopherFile` Üye işlevleri `Write`, `WriteString`, ve `Flush` için uygulanmadı `CGopherFile`. Bu işlevler çağırma bir `CGopherFile` nesnesi döndürür bir [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).

Hakkında daha fazla bilgi edinmek için `CGopherFile` diğer Internet MFC sınıfları ile çalışır, başlıklı makaleye bakın [Winınet'in Internet programlama](../../mfc/win32-internet-extensions-wininet.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[CStdioFile](../../mfc/reference/cstdiofile-class.md)

[Cınternetfile](../../mfc/reference/cinternetfile-class.md)

`CGopherFile`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxinet.h

##  <a name="cgopherfile"></a>  CGopherFile::CGopherFile

Bu üye işlevi oluşturmak için çağrılan bir `CGopherFile` nesne.

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

*Hfıle*<br/>
HINTERNET dosyaya tanıtıcı.

*refLocator*<br/>
Bir başvuru bir [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) nesne.

*pConnection*<br/>
Bir işaretçi bir [CGopherConnection](../../mfc/reference/cgopherconnection-class.md) nesne.

*hSession*<br/>
Geçerli Internet oturumu için bir tanıtıcı.

*pstrLocator*<br/>
Gopher sunucusu bulmak için kullanılan bir dizeye bir işaretçi. Bkz: [Gopher oturumları](cgopherlocator-class.md) gopher bulucuları hakkında daha fazla bilgi.

*dwLocLen*<br/>
Bayt sayısını içeren bir DWORD *pstrLocator*.

*dwContext*<br/>
Açılan dosyanın içerik tanımlayıcısı için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Gereksinim duyduğunuz bir `CGopherFile` bir gopher Internet oturumu sırasında bir dosyadan okunan nesne.

Asla oluşturma bir `CGopherFile` doğrudan nesne. Bunun yerine çağrı [CGopherConnection::OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile) bir gopher sunucusunda bir dosyayı açmak için.

## <a name="see-also"></a>Ayrıca Bkz.

[CInternetFile Sınıfı](../../mfc/reference/cinternetfile-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CInternetFile Sınıfı](../../mfc/reference/cinternetfile-class.md)<br/>
[CGopherLocator Sınıfı](../../mfc/reference/cgopherlocator-class.md)<br/>
[CGopherFileFind Sınıfı](../../mfc/reference/cgopherfilefind-class.md)<br/>
[CGopherConnection Sınıfı](../../mfc/reference/cgopherconnection-class.md)
