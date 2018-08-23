---
title: 'Nasıl yapılır: kopyalarken dilini veya koşulunu bir kaynağı değiştirme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.resvw.resource.changing
dev_langs:
- C++
helpviewer_keywords:
- Language property
- condition property of resource
ms.assetid: 8f622ab0-bac2-468f-ae70-78911afc4759
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 508655dbfeb2d06d936d2b73d5435cf04c860f4b
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42598940"
---
# <a name="how-to-change-the-language-or-condition-of-a-resource-while-copying"></a>Nasıl Yapılır: Kopyalarken Kaynağın Dilini veya Koşulunu Değiştirme

Bir kaynak olarak kopyalarken, kendi dil özelliği veya koşul özelliğini veya her ikisi de değiştirebilirsiniz.

- Kaynağın dilini yalnızca, kaynak için dil tanımlar. Tarafından kullanılan bu [FindResource](http://msdn.microsoft.com/library/windows/desktop/ms648042) , aradığınız kaynak belirlemenize yardımcı olması için. (Ancak, kaynakları farklar her metne yalnızca Japonca klavyede işe yarayabilir Hızlandırıcıları ya da yalnızca yerelleştirilmiş Çince uygun olacağı bir bit eşlem oluşturur Örneğin, ilişkili olmayan dil, vb. olabilir.)

- Bir kaynağı tanımlayan bir koşul altında kullanılacak bu belirli kaynak kopyası olan bir tanımlanmış sembol durumdur.

Dil ve kaynak durumunu çalışma alanı penceresini kaynak adından sonra parantez içinde gösterilmektedir. Bu örnekte, dil Fince IDD_AboutBox adlı kaynağın kullanıyor ve XX33 kendi durumdur.

```cpp
IDD_AboutBox (Finnish - XX33)  
```

### <a name="to-copy-an-existing-resource-and-change-its-language-or-condition"></a>Mevcut bir kaynağı kopyalayın ve kendi dilini veya koşulunu değiştirme

1. .Rc dosyasının veya [kaynak görünümü](../windows/resource-view-window.md) penceresi, kopyalamak istediğiniz kaynağa sağ tıklayın.

2. Seçin **Ekle kopyalama** kısayol menüsünden.

3. İçinde **kaynak kopyasını Ekle** iletişim kutusunda:

   - İçin **dil** liste kutusunda, bir dil seçin.

   - İçinde **koşul** koşul yazın.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Nasıl yapılır: Kaynakları Kopyalama](../windows/how-to-copy-resources.md)  
[Kaynak dosyaları](../windows/resource-files-visual-studio.md)  
[Kaynak Düzenleyicileri](../windows/resource-editors.md)