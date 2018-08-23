---
title: Sembolü veya sembol adını (ID) değiştirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.symbol.changing
dev_langs:
- C++
helpviewer_keywords:
- symbol names
- symbols, names
ms.assetid: 26541832-8dba-4177-b642-e08f94502ea7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e2fb5268ca23def96c31f724b93fbdf1c81c4a43
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42599701"
---
# <a name="changing-a-symbol-or-symbol-name-id"></a>Sembolü veya Sembol Adını (ID) Değiştirme

Yeni bir kaynak veya kaynak nesnesi oluşturduğunuzda, geliştirme ortamı varsayılan sembol adı, örneğin, IDD_DIALOG1 atar. Kullanabileceğiniz [Özellikler penceresi](/visualstudio/ide/reference/properties-window) varsayılan sembol adı değiştirmek veya zaten bir kaynakla ilişkilendirilmiş herhangi bir sembol adını değiştirmek için.

### <a name="to-change-a-resources-symbol-name"></a>Bir kaynağın sembol adını değiştirmek için

1. İçinde [kaynak görünümü](../windows/resource-view-window.md), kaynağı seçin.

   > [!NOTE]
   > Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

2. İçinde **özellikleri** penceresinde, yeni bir sembol adı yazın veya mevcut simgeler listesinden **kimliği** kutusu.

   Yeni bir sembol adı yazdığınızda, değer otomatik olarak atanır.

Kullanabileceğiniz [kaynak sembolleri iletişim kutusu](../windows/resource-symbols-dialog-box.md) bir kaynağa atanmış sembol adlarını değiştirmek için. Daha fazla bilgi için [atanmamış sembolleri değiştirme](../windows/changing-unassigned-symbols.md).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Sembol Adı Kısıtlamaları](../windows/symbol-name-restrictions.md)  
[Önceden Tanımlanmış Sembol Kimlikleri](../windows/predefined-symbol-ids.md)