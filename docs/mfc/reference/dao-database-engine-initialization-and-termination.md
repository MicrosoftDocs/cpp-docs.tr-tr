---
description: 'Daha fazla bilgi edinin: DAO veritabanı altyapısı başlatma ve sonlandırma'
title: DAO Veritabanı Motoru Başlatma ve Sonlandırma
ms.date: 09/17/2019
helpviewer_keywords:
- DAO (Data Access Objects), termination
- DAO (Data Access Objects), initialization
ms.assetid: a7edf31c-e7c2-4f3e-aada-63c3e48781da
ms.openlocfilehash: 9e9b522d744eabc84074b201051151b80ed75d7e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220402"
---
# <a name="dao-database-engine-initialization-and-termination"></a>DAO Veritabanı Motoru Başlatma ve Sonlandırma

DAO, Access veritabanları ile birlikte kullanılır ve Office 2013 aracılığıyla desteklenir. DAO 3,6 son sürümdür ve artık kullanılmıyor olarak kabul edilir. MFC DAO nesneleri kullanılırken, önce DAO veritabanı altyapısının başlatılması ve sonra uygulamanız veya DLL 'den sonlandırılmadan önce sonlandırılması gerekir. İki işlev `AfxDaoInit` ve `AfxDaoTerm` Bu görevleri gerçekleştirir.

### <a name="dao-database-engine-initialization-and-termination"></a>DAO Veritabanı Motoru Başlatma ve Sonlandırma

|Ad|Açıklama|
|-|-|
|[AfxDaoInit](#afxdaoinit)|DAO veritabanı altyapısını başlatır.|
|[AfxDaoTerm](#afxdaoterm)|DAO veritabanı altyapısını sonlandırır.|

## <a name="afxdaoinit"></a><a name="afxdaoinit"></a> AfxDaoInit

Bu işlev, DAO veritabanı altyapısını başlatır.

```

void AfxDaoInit();

throw(CDaoException*);
```

### <a name="remarks"></a>Açıklamalar

Çoğu durumda, `AfxDaoInit` uygulama gerektiğinde otomatik olarak çağırdığı için çağrı yapmanız gerekmez.

İlgili bilgiler ve çağrı bir örnek için `AfxDaoInit` bkz. [teknik notta 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).

### <a name="requirements"></a>Gereksinimler

  **Header** afxdao. h

## <a name="afxdaoterm"></a><a name="afxdaoterm"></a> AfxDaoTerm

Bu işlev, DAO veritabanı altyapısını sonlandırır.

```

void AfxDaoTerm();
```

### <a name="remarks"></a>Açıklamalar

Genellikle, bu işlevi yalnızca normal bir MFC DLL 'de çağırmanız gerekir; bir uygulama gerektiğinde otomatik olarak çağracaktır `AfxDaoTerm` .

Normal MFC DLL 'Lerinde, `AfxDaoTerm` işlevden önce çağırın `ExitInstance` , ancak tüm MFC DAO nesneleri yok edilir.

İlgili bilgiler için bkz. [teknik notta 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).

### <a name="requirements"></a>Gereksinimler

  **Header** afxdao. h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve genel öğeler](../../mfc/reference/mfc-macros-and-globals.md)
