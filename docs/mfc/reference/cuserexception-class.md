---
description: 'Daha fazla bilgi edinin: CUserException sınıfı'
title: CUserException sınıfı
ms.date: 11/04/2016
f1_keywords:
- CUserException
helpviewer_keywords:
- operations [MFC], stopping
- exceptions [MFC], throwing
- CUserException class [MFC]
- errors [MFC], trapping
- operations [MFC]
- throwing exceptions [MFC], stopping user operations
ms.assetid: 2156ba6d-2cce-415a-9000-6f02c26fcd7d
ms.openlocfilehash: 6104aa2883a80f88aed03634f09ad1947e9c6794
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344971"
---
# <a name="cuserexception-class"></a>CUserException sınıfı

Son Kullanıcı işlemini durdurmak için oluşturulur.

## <a name="syntax"></a>Syntax

```
class CUserException : public CSimpleException
```

## <a name="remarks"></a>Açıklamalar

`CUserException`Uygulamaya özel özel durumlar için throw/catch özel durum mekanizmasını kullanmak istediğinizde kullanın. Sınıf adı içindeki "user", "My User bir şeyi ele almam gerekiyor" olarak yorumlanabilir.

`CUserException`Genellikle, `AfxMessageBox` kullanıcıya bir işlemin başarısız olduğunu bildirmek için genel işlev çağrıldıktan sonra oluşturulur. Bir özel durum işleyicisi yazdığınızda, Kullanıcı genellikle hatanın zaten bilgilendirildi olduğundan özel durumu özel olarak işleyin. Framework, bazı durumlarda bu özel durumu atar. Kendiniz oluşturmak için `CUserException` kullanıcıyı uyarın ve sonra genel işlevini çağırın `AfxThrowUserException` .

Aşağıdaki örnekte, başarısız olabilecek işlemleri içeren bir işlev, kullanıcıyı uyarır ve bir oluşturur `CUserException` . Çağırma işlevi özel durumu yakalar ve özel olarak işler:

[!code-cpp[NVC_MFCExceptions#24](../../mfc/codesnippet/cpp/cuserexception-class_1.cpp)]

Kullanma hakkında daha fazla bilgi için `CUserException` bkz. [özel durum Işleme (MFC)](../../mfc/exception-handling-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

[CSimpleException](../../mfc/reference/csimpleexception-class.md)

`CUserException`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CException sınıfı](../../mfc/reference/cexception-class.md)
