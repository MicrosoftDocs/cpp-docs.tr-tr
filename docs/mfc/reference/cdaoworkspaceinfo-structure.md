---
title: CDaoWorkspaceInfo Yapısı
ms.date: 11/04/2016
f1_keywords:
- CDaoWorkspaceInfo
helpviewer_keywords:
- CDaoWorkspaceInfo structure [MFC]
- DAO (Data Access Objects), Workspaces collection
ms.assetid: a1f4b25e-f9c6-4196-b075-d1df99c54124
ms.openlocfilehash: e47df7323d130bee2a378a4cf7dcae8001641f6e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50562818"
---
# <a name="cdaoworkspaceinfo-structure"></a>CDaoWorkspaceInfo Yapısı

`CDaoWorkspaceInfo` Yapısı için veri erişim nesneleri (DAO) veritabanı erişimi tanımlanan bir çalışma alanı hakkında bilgi içerir.

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
Çalışma alanı nesnesi benzersiz olarak adlandırır. Doğrudan bu özelliğin değerini almak için querydef nesnesinin çağrı [GetName](../../mfc/reference/cdaoquerydef-class.md#getname) üye işlevi. Daha fazla bilgi için "Name özelliği" DAO Yardım konusuna bakın.

*m_strUserName*<br/>
Bir çalışma alanı nesnenin sahibi temsil eden bir değer. İlgili bilgiler için DAO Yardımı'nda "UserName özelliği" konusuna bakın.

*m_bIsolateODBCTrans*<br/>
Aynı ODBC veritabanı içeren birden çok işlem yalıtılmış olup olmadığını belirten bir değer. Daha fazla bilgi için [CDaoWorkspace::SetIsolateODBCTrans](../../mfc/reference/cdaoworkspace-class.md#setisolateodbctrans). İlgili bilgiler için DAO Yardımı'nda "IsolateODBCTrans özelliği" konusuna bakın.

## <a name="remarks"></a>Açıklamalar

Sınıfın bir nesnesi çalışma alanıdır [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md). Birincil, ikincil ve yukarıdaki tüm başvuruları nasıl bilgileri tarafından döndürülen belirtmek [GetWorkspaceInfo](../../mfc/reference/cdaoworkspace-class.md#getworkspaceinfo) sınıf üyesi işlevinde `CDaoWorkspace`.

Tarafından alınan bilgileri [CDaoWorkspace::GetWorkspaceInfo](../../mfc/reference/cdaoworkspace-class.md#getworkspaceinfo) üye işlevi depolanan bir `CDaoWorkspaceInfo` yapısı. `CDaoWorkspaceInfo` Ayrıca tanımlayan bir `Dump` hata ayıklama üye işlevinde oluşturur. Kullanabileceğiniz `Dump` içeriğini dökümünü almak için bir `CDaoWorkspaceInfo` nesne.

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdao.h

## <a name="see-also"></a>Ayrıca Bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoWorkspace Sınıfı](../../mfc/reference/cdaoworkspace-class.md)
