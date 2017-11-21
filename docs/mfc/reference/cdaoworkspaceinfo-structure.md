---
title: "Cdaoworkspaceınfo yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CDaoWorkspaceInfo
dev_langs: C++
helpviewer_keywords:
- CDaoWorkspaceInfo structure [MFC]
- DAO (Data Access Objects), Workspaces collection
ms.assetid: a1f4b25e-f9c6-4196-b075-d1df99c54124
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 90c4fced8be41ea7266b144a95875be3fbfb5a41
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cdaoworkspaceinfo-structure"></a>CDaoWorkspaceInfo Yapısı
`CDaoWorkspaceInfo` Yapısı veri erişim nesnesi (DAO) veritabanı erişimi için tanımlanmış bir çalışma alanı hakkında bilgiler içerir.  
  
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
 `m_strName`  
 Çalışma alanı nesnesi adlandıran. Bu özelliğin değerini doğrudan almak için querydef nesnesinin çağrısı [GetName](../../mfc/reference/cdaoquerydef-class.md#getname) üye işlevi. Daha fazla bilgi için DAO Yardımı'ndaki "Name özelliği" konusuna bakın.  
  
 *m_strUserName*  
 Bir çalışma alanı nesnenin sahibi temsil eden bir değer. İlgili bilgi için DAO Yardımı'ndaki "UserName özelliği" konusuna bakın.  
  
 *m_bIsolateODBCTrans*  
 Aynı ODBC veritabanı içeren birden çok işlem yalıtılmış olup olmadığını belirten bir değer. Daha fazla bilgi için bkz: [CDaoWorkspace::SetIsolateODBCTrans](../../mfc/reference/cdaoworkspace-class.md#setisolateodbctrans). İlgili bilgi için DAO Yardımı'ndaki "IsolateODBCTrans özelliği" konusuna bakın.  
  
## <a name="remarks"></a>Açıklamalar  
 Sınıfın bir nesnesi çalışma alanıdır [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md). Birincil, ikincil ve yukarıdaki tüm başvuruları nasıl bilgileri tarafından döndürülen belirtmek [GetWorkspaceInfo](../../mfc/reference/cdaoworkspace-class.md#getworkspaceinfo) üye işlevi sınıfında `CDaoWorkspace`.  
  
 Tarafından alınan bilgileri [CDaoWorkspace::GetWorkspaceInfo](../../mfc/reference/cdaoworkspace-class.md#getworkspaceinfo) üye işlevi depolanır bir `CDaoWorkspaceInfo` yapısı. `CDaoWorkspaceInfo`Ayrıca tanımlayan bir `Dump` hata ayıklama üye işlevinde oluşturur. Kullanabileceğiniz `Dump` içeriğini dökümü bir `CDaoWorkspaceInfo` nesnesi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdao.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri aramalar ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoWorkspace sınıfı](../../mfc/reference/cdaoworkspace-class.md)
