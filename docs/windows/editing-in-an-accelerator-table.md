---
title: Hızlandırıcı tablosunu düzenleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- accelerator tables [C++], editing
- keyboard shortcuts [C++], editing in an accelerator table
ms.assetid: 545b650b-4f26-4b20-8431-d942548443bd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ed8e2b630444c28675b4714b65676a049a8b285b
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42611103"
---
# <a name="editing-in-an-accelerator-table"></a>Hızlandırıcı Tablosunu Düzenleme

### <a name="to-edit-in-an-accelerator-table"></a>Hızlandırıcı tablosunu düzenleme

1. Hızlandırıcı tablosu simgeye çift tıklayarak açın [kaynak görünümü](../windows/resource-view-window.md).

   > [!NOTE]
   > Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

2. Bir giriş tablosunda seçin ve yerinde düzenlemeyi etkinleştirmek için tıklayın.

3. Açılan birleşik giriş kutusundan seçin veya değişiklik yerinde yazın.

   - İçin [kimliği](id-property.md)listesinden veya düzenlemek için türü seçin.

   - İçin [değiştiricisi](../windows/accelerator-modifier-property.md)listeden seçin.

   - İçin [anahtar](../windows/accelerator-key-property.md)listesinden veya düzenlemek için türü seçin.

   - İçin [türü](../windows/accelerator-type-property.md)seçin **ASCII** veya **VIRTKEY'e** listeden.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Hızlandırıcı Tablolarını Düzenleme](../windows/editing-accelerator-tables.md)  
[Hızlandırıcı Düzenleyicisi](../windows/accelerator-editor.md)