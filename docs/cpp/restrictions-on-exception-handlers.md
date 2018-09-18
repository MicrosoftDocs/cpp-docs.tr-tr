---
title: Özel durum işleyicileri kısıtlamaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- restrictions, exception handlers
- exception handling [C++], exception handlers
ms.assetid: 31d63524-0e8c-419f-b87c-061f4c0ea470
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 29a462f83bff3bab158e9bcf9fa7947efb56a79b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46074480"
---
# <a name="restrictions-on-exception-handlers"></a>Özel Durum İşleyicileri Kısıtlamaları

Kodda özel durum işleyicileri kullanmaya ilişkin birincil sınırlama, kullanamazsınız olduğu bir **goto** bloğuna atlamak için bir **__try** deyim bloğu. Bunun yerine, normal denetim akışıyla deyim bloğunu girmeniz gerekir. / Hızlı bir **__try** deyimi engelleme ve seçtiğiniz özel durum işleyicilerini iç içe yerleştirebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleyicisi Yazma](../cpp/writing-an-exception-handler.md)<br/>
[Yapılandırılmış Özel Durum İşleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)