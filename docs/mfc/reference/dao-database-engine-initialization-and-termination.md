---
title: DAO Veritabanı Motoru Başlatma ve Sonlandırma
ms.date: 09/17/2019
helpviewer_keywords:
- DAO (Data Access Objects), termination
- DAO (Data Access Objects), initialization
ms.assetid: a7edf31c-e7c2-4f3e-aada-63c3e48781da
ms.openlocfilehash: 24a24d5a81da18d01472fc760c2adf96ee9868d5
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74303464"
---
# <a name="dao-database-engine-initialization-and-termination"></a>DAO Veritabanı Motoru Başlatma ve Sonlandırma

DAO, Access veritabanları ile birlikte kullanılır ve Office 2013 aracılığıyla desteklenir. DAO 3,6 son sürümdür ve artık kullanılmıyor olarak kabul edilir. MFC DAO nesneleri kullanılırken, önce DAO veritabanı altyapısının başlatılması ve sonra uygulamanız veya DLL 'den sonlandırılmadan önce sonlandırılması gerekir. İki işlev, `AfxDaoInit` ve `AfxDaoTerm`, bu görevleri gerçekleştirir.

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

Çoğu durumda, uygulama gerektiği zaman otomatik olarak çağırdığı için `AfxDaoInit` çağırmanız gerekmez.

İlgili bilgiler için ve `AfxDaoInit`çağırma hakkında bir örnek için bkz. [teknik notta 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).

### <a name="requirements"></a>Gereksinimler

  **Header** afxdao. h

##  <a name="afxdaoterm"></a>AfxDaoTerm

Bu işlev, DAO veritabanı altyapısını sonlandırır.

```

void AfxDaoTerm();
```

### <a name="remarks"></a>Açıklamalar

Genellikle, bu işlevi yalnızca normal bir MFC DLL 'de çağırmanız gerekir; bir uygulama, gerektiğinde `AfxDaoTerm` otomatik olarak çağıracaktır.

Normal MFC DLL 'Lerinde, `ExitInstance` işlevinden önce `AfxDaoTerm` çağırın, ancak tüm MFC DAO nesneleri yok edilir.

İlgili bilgiler için bkz. [teknik notta 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).

### <a name="requirements"></a>Gereksinimler

  **Header** afxdao. h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve genel öğeler](../../mfc/reference/mfc-macros-and-globals.md)
