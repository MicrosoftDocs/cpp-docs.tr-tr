---
title: DAO Veritabanı Motoru Başlatma ve Sonlandırma
ms.date: 09/17/2019
helpviewer_keywords:
- DAO (Data Access Objects), termination
- DAO (Data Access Objects), initialization
ms.assetid: a7edf31c-e7c2-4f3e-aada-63c3e48781da
ms.openlocfilehash: 62460e8e55f70b8cb0743f1d044636d25121050d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365901"
---
# <a name="dao-database-engine-initialization-and-termination"></a>DAO Veritabanı Motoru Başlatma ve Sonlandırma

DAO Access veritabanları ile kullanılır ve Office 2013 aracılığıyla desteklenir. DAO 3.6 son sürümüdür ve eski miş olarak kabul edilir. MFC DAO nesneleri kullanırken, DAO veritabanı altyapısı önce baş harfe çevrilmeli ve uygulamanız veya DLL çıkmadan önce sonlandırılmalıdır. İki işlev `AfxDaoInit` `AfxDaoTerm`ve , bu görevleri gerçekleştirin.

### <a name="dao-database-engine-initialization-and-termination"></a>DAO Veritabanı Motoru Başlatma ve Sonlandırma

|||
|-|-|
|[AfxDaoInit](#afxdaoinit)|DAO veritabanı altyapısını çalıştırıyor.|
|[AfxDaoTerm](#afxdaoterm)|DAO veritabanı altyapısını sonlandırır.|

## <a name="afxdaoinit"></a><a name="afxdaoinit"></a>AfxDaoInit

Bu işlev DAO veritabanı altyapısını çalıştırıyor.

```

void AfxDaoInit();

throw(CDaoException*);
```

### <a name="remarks"></a>Açıklamalar

Çoğu durumda, uygulama gerektiğinde otomatik `AfxDaoInit` olarak aradığından aramanız gerekmez.

İlgili bilgiler ve arama `AfxDaoInit`örneği için [Teknik Not 54'e](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)bakın.

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxdao.h

## <a name="afxdaoterm"></a><a name="afxdaoterm"></a>AfxDaoTerm

Bu işlev DAO veritabanı altyapısını sonlandırır.

```

void AfxDaoTerm();
```

### <a name="remarks"></a>Açıklamalar

Genellikle, bu işlevi yalnızca normal bir MFC DLL'de aramanız gerekir; bir uygulama gerektiğinde `AfxDaoTerm` otomatik olarak arayacaktır.

Normal MFC DL'lerde, `AfxDaoTerm` işlevden `ExitInstance` önce arayın, ancak tüm MFC DAO nesneleri yok edildikten sonra.

İlgili bilgiler için [Teknik Not 54'e](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)bakın.

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxdao.h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve Küreseller](../../mfc/reference/mfc-macros-and-globals.md)
