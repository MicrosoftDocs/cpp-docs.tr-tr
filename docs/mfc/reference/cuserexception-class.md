---
title: CUserException sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CUserException
dev_langs:
- C++
helpviewer_keywords:
- operations [MFC], stopping
- exceptions [MFC], throwing
- CUserException class [MFC]
- errors [MFC], trapping
- operations [MFC]
- throwing exceptions [MFC], stopping user operations
ms.assetid: 2156ba6d-2cce-415a-9000-6f02c26fcd7d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 71d2be1c00e518597a5d5121d7a53544bd29067f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46419665"
---
# <a name="cuserexception-class"></a>CUserException sınıfı

Son kullanıcı işlemini durdurmak için oluşturulur.

## <a name="syntax"></a>Sözdizimi

```
class CUserException : public CSimpleException
```

## <a name="remarks"></a>Açıklamalar

Kullanma `CUserException` throw/catch özel durum mekanizması için uygulamaya özgü özel durumlar kullanmak istediğinizde. Sınıf adı "kullanıcı", "my kullanıcı işlemek gereken olağanüstü bir sorun oldu."olarak yorumlanabilir

A `CUserException` genellikle genel işlev çağrıldıktan sonra durum `AfxMessageBox` bir işlem başarısız oldu kullanıcıya bildirmek için. Özel durum işleyicisi yazdığınızda, özel kullanıcı genellikle zaten hata bildirildi olduğundan özel durumu işle. Framework, bazı durumlarda bu özel durum oluşturur. Oluşturulacak bir `CUserException` kendiniz kullanıcıyı uyarmak ve ardından genel işlev çağrısı `AfxThrowUserException`.

Aşağıdaki örnekte, başarısız işlemler içeren bir işlev kullanıcıyı uyarır ve oluşturur bir `CUserException`. Çağıran işlevin özel durumu yakalar ve özel olarak işler:

[!code-cpp[NVC_MFCExceptions#24](../../mfc/codesnippet/cpp/cuserexception-class_1.cpp)]

Kullanma hakkında daha fazla bilgi için `CUserException`, makaleye göz atın [özel durum işleme (MFC)](../../mfc/exception-handling-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

[CSimpleException](../../mfc/reference/csimpleexception-class.md)

`CUserException`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxwin.h

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CException Sınıfı](../../mfc/reference/cexception-class.md)
