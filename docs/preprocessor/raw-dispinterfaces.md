---
description: 'Hakkında daha fazla bilgi edinin: raw_dispinterfaces Import özniteliği'
title: raw_dispinterfaces içeri aktarma özniteliği
ms.date: 08/29/2019
f1_keywords:
- raw_dispinterfaces
helpviewer_keywords:
- raw_dispinterfaces attribute
ms.assetid: f762864d-29bf-445b-825a-ba7b29a95409
ms.openlocfilehash: 447f76bdee16d2719c02ad4a73883f8f176f2584
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202021"
---
# <a name="raw_dispinterfaces-import-attribute"></a>raw_dispinterfaces içeri aktarma özniteliği

**C++ özel**

Derleyiciye, dispınterface yöntemleri için alt düzey sarmalayıcı işlevleri oluşturmasını ve `IDispatch::Invoke` hresult hata kodunu çağıran ve döndüren özellikler için söyler.

## <a name="syntax"></a>Syntax

> **#import** *türü-kitaplık* **raw_dispinterfaces**

## <a name="remarks"></a>Açıklamalar

Bu öznitelik belirtilmemişse, hata durumunda C++ özel durumları oluşturan yalnızca üst düzey sarmalayıcılar oluşturulur.

**Son C++ özel**

## <a name="see-also"></a>Ayrıca bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)\
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)
