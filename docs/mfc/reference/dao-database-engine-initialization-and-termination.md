---
title: DAO Veritabanı Motoru Başlatma ve Sonlandırma
ms.date: 09/17/2019
helpviewer_keywords:
- DAO (Data Access Objects), termination
- DAO (Data Access Objects), initialization
ms.assetid: a7edf31c-e7c2-4f3e-aada-63c3e48781da
ms.openlocfilehash: ccdf2e7b0f31576dddccad016e6b32806cdb82bf
ms.sourcegitcommit: 2f96e2fda591d7b1b28842b2ea24e6297bcc3622
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2019
ms.locfileid: "71095879"
---
# <a name="dao-database-engine-initialization-and-termination"></a>DAO Veritabanı Motoru Başlatma ve Sonlandırma

DAO, Access veritabanları ile birlikte kullanılır ve Office 2013 aracılığıyla desteklenir. 3,6 son sürümdür ve artık kullanılmıyor olarak kabul edilir. MFC DAO nesneleri kullanılırken, önce DAO veritabanı altyapısının başlatılması ve sonra uygulamanız veya DLL 'den sonlandırılmadan önce sonlandırılması gerekir. İki işlev `AfxDaoInit` ve `AfxDaoTerm`bu görevleri gerçekleştirir.

### <a name="dao-database-engine-initialization-and-termination"></a>DAO Veritabanı Motoru Başlatma ve Sonlandırma

|||
|-|-|
|[AfxDaoInit](#afxdaoinit)|DAO veritabanı altyapısını başlatır.|
|[AfxDaoTerm](#afxdaoterm)|DAO veritabanı altyapısını sonlandırır.|

##  <a name="afxdaoinit"></a>AfxDaoInit

Bu işlev, DAO veritabanı altyapısını başlatır.

```

void AfxDaoInit();

throw(CDaoException*);
```

### <a name="remarks"></a>Açıklamalar

Çoğu durumda, uygulama gerektiğinde otomatik olarak çağırdığı için `AfxDaoInit` çağrı yapmanız gerekmez.

İlgili bilgiler ve çağrı `AfxDaoInit`bir örnek için bkz. [teknik notta 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).

### <a name="requirements"></a>Gereksinimler

  **Header** afxdao. h

##  <a name="afxdaoterm"></a>AfxDaoTerm

Bu işlev, DAO veritabanı altyapısını sonlandırır.

```

void AfxDaoTerm();
```

### <a name="remarks"></a>Açıklamalar

Genellikle, bu işlevi yalnızca normal bir MFC DLL 'de çağırmanız gerekir; bir uygulama gerektiğinde otomatik olarak `AfxDaoTerm` çağracaktır.

Normal MFC DLL 'lerinde, `AfxDaoTerm` `ExitInstance` işlevden önce çağırın, ancak tüm MFC DAO nesneleri yok edilir.

İlgili bilgiler için bkz. [teknik notta 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).

### <a name="requirements"></a>Gereksinimler

  **Header** afxdao. h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve genel öğeler](../../mfc/reference/mfc-macros-and-globals.md)
