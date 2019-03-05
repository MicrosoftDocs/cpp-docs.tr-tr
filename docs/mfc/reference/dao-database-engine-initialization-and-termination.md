---
title: DAO Veritabanı Motoru Başlatma ve Sonlandırma
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.macros.data
helpviewer_keywords:
- DAO (Data Access Objects), termination
- DAO (Data Access Objects), initialization
ms.assetid: a7edf31c-e7c2-4f3e-aada-63c3e48781da
ms.openlocfilehash: 8ad0c1df2f5b6a7b1b48d2db119b04e4b3234f10
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57297647"
---
# <a name="dao-database-engine-initialization-and-termination"></a>DAO Veritabanı Motoru Başlatma ve Sonlandırma

MFC DAO nesneleri kullanırken DAO veritabanı motoru ilk olarak başlatılır ve ardından sona uygulamanızı veya DLL sonlandırılmadan önce. İki işlev `AfxDaoInit` ve `AfxDaoTerm`, şu görevleri gerçekleştirebilirsiniz.

### <a name="dao-database-engine-initialization-and-termination"></a>DAO Veritabanı Motoru Başlatma ve Sonlandırma

|||
|-|-|
|[Afxdaoınit](#afxdaoinit)|DAO veritabanı motoru başlatır.|
|[AfxDaoTerm](#afxdaoterm)|DAO veritabanı motoru sonlandırır.|

##  <a name="afxdaoinit"></a>  Afxdaoınit

Bu işlev DAO veritabanı motoru başlatır.

```

void AfxDaoInit();

throw(CDaoException*);
```

### <a name="remarks"></a>Açıklamalar

Çoğu durumda, çağrı gerekmez `AfxDaoInit` çünkü gerektiğinde uygulama otomatik olarak çağırır.

İlgili bilgi ve arama örneği için `AfxDaoInit`, bkz: [Teknik Not 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdao.h

##  <a name="afxdaoterm"></a>  AfxDaoTerm

Bu işlev DAO veritabanı motoru sonlandırır.

```

void AfxDaoTerm();
```

### <a name="remarks"></a>Açıklamalar

Genellikle, bir Normal MFC DLL bu işlevi çağırın yeterlidir; bir uygulamayı otomatik olarak çağıran `AfxDaoTerm` ne zaman yapılması gerekiyor.

Normal MFC DLL'lerinde çağrı `AfxDaoTerm` önce `ExitInstance` işlevi, ancak tüm MFC DAO nesneleri yok edildikten sonra sonra.

İlgili bilgiler için bkz. [Teknik Not 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdao.h

## <a name="see-also"></a>Ayrıca bkz.

[Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)
