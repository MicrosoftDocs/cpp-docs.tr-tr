---
title: raw_dispinterfaces içeri aktarma özniteliği
ms.date: 08/29/2019
f1_keywords:
- raw_dispinterfaces
helpviewer_keywords:
- raw_dispinterfaces attribute
ms.assetid: f762864d-29bf-445b-825a-ba7b29a95409
ms.openlocfilehash: 73c58b72b27de8dcf96e8ab9464d0fb6bce12b66
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216218"
---
# <a name="raw_dispinterfaces-import-attribute"></a>raw_dispinterfaces içeri aktarma özniteliği

**C++Belirli**

Derleyiciye, dispınterface yöntemleri için alt düzey sarmalayıcı işlevleri oluşturmasını ve hresult hata kodunu çağıran `IDispatch::Invoke` ve döndüren özellikler için söyler.

## <a name="syntax"></a>Sözdizimi

> **#import** *tür kitaplığı* **raw_dispinterfaces**

## <a name="remarks"></a>Açıklamalar

Bu öznitelik belirtilmemişse, hata durumunda C++ özel durumlar oluşturan yalnızca üst düzey sarmalayıcılar oluşturulur.

**SONA C++ özgü**

## <a name="see-also"></a>Ayrıca bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)\
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)
