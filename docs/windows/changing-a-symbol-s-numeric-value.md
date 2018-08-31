---
title: Bir sembol değiştirme&#39;s sayısal değer | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.symbol.changing.value
dev_langs:
- C++
helpviewer_keywords:
- numeric values
- symbols, numeric values
- numeric values, changing symbols
ms.assetid: 468e903b-9c07-4251-ae09-3b6cb754cc2b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c05c732f87434754fb6776d7f914b4ffa5c26015
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43219282"
---
# <a name="changing-a-symbol39s-numeric-value"></a>Bir sembol değiştirme&#39;s sayısal değer

Tek bir kaynakla ilişkili semboller için kullanabileceğiniz [Özellikler penceresi](/visualstudio/ide/reference/properties-window) sembol değeri değiştirmek için. Kullanabileceğiniz [kaynak sembolleri iletişim kutusu](../windows/resource-symbols-dialog-box.md) sembolleri bir kaynağa atanmış değerini değiştirin. Daha fazla bilgi için [atanmamış sembolleri değiştirme](../windows/changing-unassigned-symbols.md).

### <a name="to-change-a-symbol-value-assigned-to-a-single-resource-or-object"></a>Bir tek bir kaynak veya nesne atanmış bir simge değerini değiştirmek için

1. İçinde [kaynak görünümü](../windows/resource-view-window.md), kaynağı seçin.

   > [!NOTE]
   > Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

2. İçinde **özellikleri** penceresinde, tür sembol adı ve ardından bir eşittir işareti ve bir tamsayı olarak **kimliği** kutusunda, örneğin:

    ```
    IDC_EDITNAME=5100
    ```

Yeni değer proje kaydettiğinizde sembol üstbilgi dosyasında depolanır. Sembol adı kimliği kutusuna görünür kalır; Bunlar doğrulandıktan sonra eşittir işareti ve değer görüntülenmez.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere, kaynaklara erişme, el ile ekleme hakkında bilgi için statik kaynakları görüntüleme ve kaynak atama özellikleri dizeler.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Sembol Değeri Kısıtlamaları](../windows/symbol-value-restrictions.md)  
[Önceden Tanımlanmış Sembol Kimlikleri](../windows/predefined-symbol-ids.md)