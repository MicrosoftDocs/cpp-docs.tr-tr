---
description: 'Daha fazla bilgi edinin: CDaoWorkspace bilgi yapısı'
title: CDaoWorkspaceInfo Yapısı
ms.date: 11/04/2016
f1_keywords:
- CDaoWorkspaceInfo
helpviewer_keywords:
- CDaoWorkspaceInfo structure [MFC]
- DAO (Data Access Objects), Workspaces collection
ms.assetid: a1f4b25e-f9c6-4196-b075-d1df99c54124
ms.openlocfilehash: b89e8787c2103244535e9458650f1f104478b748
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222209"
---
# <a name="cdaoworkspaceinfo-structure"></a>CDaoWorkspaceInfo Yapısı

`CDaoWorkspaceInfo`Yapı, veri erişim nesneleri (DAO) veritabanı erişimi için tanımlanan bir çalışma alanıyla ilgili bilgiler içerir.

## <a name="syntax"></a>Sözdizimi

```
struct CDaoWorkspaceInfo
{
    CString m_strName;           // Primary
    CString m_strUserName;       // Secondary
    BOOL m_bIsolateODBCTrans;    // All
};
```

#### <a name="parameters"></a>Parametreler

*m_strName*<br/>
Çalışma alanı nesnesini benzersiz olarak adlandırır. Bu özelliğin değerini doğrudan almak için, QueryDef nesnesinin [GetName](../../mfc/reference/cdaoquerydef-class.md#getname) üye işlevini çağırın. Daha fazla bilgi için, DAO yardımı 'nda "ad özelliği" konusuna bakın.

*m_strUserName*<br/>
Bir çalışma alanı nesnesinin sahibini temsil eden bir değer. İlgili bilgiler için, DAO yardımı 'nda "Kullanıcı adı özelliği" konusuna bakın.

*m_bIsolateODBCTrans*<br/>
Aynı ODBC veritabanını içeren birden çok işlem yalıtılmış olup olmadığını gösteren bir değer. Daha fazla bilgi için bkz. [CDaoWorkspace:: SetIsolateODBCTrans](../../mfc/reference/cdaoworkspace-class.md#setisolateodbctrans). İlgili bilgiler için, DAO yardımı 'nda "ısoteodbctrans özelliği" konusuna bakın.

## <a name="remarks"></a>Açıklamalar

Çalışma alanı, [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)sınıfının bir nesnesidir. Yukarıdaki birincil, Ikincil ve tüm başvurular, bilgilerin sınıfında [Getıgnınfo](../../mfc/reference/cdaoworkspace-class.md#getworkspaceinfo) üye işlevi tarafından nasıl döndürüleceğini gösterir `CDaoWorkspace` .

[CDaoWorkspace:: Getıgnınfo](../../mfc/reference/cdaoworkspace-class.md#getworkspaceinfo) üye işlevi tarafından alınan bilgiler bir `CDaoWorkspaceInfo` yapıda depolanıyor. `CDaoWorkspaceInfo` Ayrıca `Dump` , hata ayıklama yapılarında bir üye işlevi tanımlar. `Dump`Bir nesnenin içeriğini dökmek için kullanabilirsiniz `CDaoWorkspaceInfo` .

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao. h

## <a name="see-also"></a>Ayrıca bkz.

[Yapılar, stiller, geri çağrılar ve Ileti haritaları](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoWorkspace sınıfı](../../mfc/reference/cdaoworkspace-class.md)
