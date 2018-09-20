---
title: DAO veritabanı motoru başlatma ve sonlandırma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros.data
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), termination
- DAO (Data Access Objects), initialization
ms.assetid: a7edf31c-e7c2-4f3e-aada-63c3e48781da
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8cf54992896559f1b143247746ef9f9e0e8d8979
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46404013"
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

## <a name="see-also"></a>Ayrıca Bkz.

[Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)
