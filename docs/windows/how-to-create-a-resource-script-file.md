---
title: 'Nasıl yapılır: kaynak betik dosyası oluştur | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- rc files, creating
- .rc files, creating
- resource script files, creating
ms.assetid: 82be732a-cdcd-4a58-8de7-976d1418f86b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8b07efbd4f1434992c76de2b7e959f4578d60096
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42608743"
---
# <a name="how-to-create-a-resource-script-file"></a>Nasıl Yapılır: Kaynak Betik Dosyası Oluşturma

> [!NOTE]
> **Kaynak Düzenleyicisi** Express sürümlerinde kullanılamaz.
>
> Bu yazıda, Windows Masaüstü uygulamaları için geçerlidir. .NET dilleri projelerde kaynak betik dosyalarına kullanmayın. Bkz: [kaynak dosyaları](../windows/resource-files-visual-studio.md), daha fazla bilgi için.

### <a name="to-create-a-new-resource-script-rc-file"></a>Yeni bir kaynak betiği (.rc) dosyası oluşturmak için

1. Mevcut proje klasörünüzde odak yerleştirin **Çözüm Gezgini**, örneğin, `MyProject`.

   > [!NOTE]
   > Proje klasörü çözüm klasöründe ile karıştırmayın **Çözüm Gezgini**. Odak moduna geçirirseniz **çözüm** klasörü, seçimlerinize **Yeni Öğe Ekle** iletişim kutusunda (3. adım) farklı olacaktır.

2. Üzerinde **proje** menüsünü tıklatın **Yeni Öğe Ekle**.

3. İçinde **Yeni Öğe Ekle** iletişim kutusu, tıklayın **Visual C++** klasörü seçin **kaynak dosyası (.rc)** sağ bölmede.

4. Kaynak kod dosyanız için bir ad sağlayın **adı** metin kutusunu işaretleyip tıklayın **açık**.

Artık [oluşturma](../windows/how-to-create-a-resource.md) ve yeni kaynaklar, .rc dosyasına ekleyin.

> [!NOTE]
> Kaynak betiği (.rc dosyası) yalnızca Visual Studio IDE'ye yüklenir, varolan bir projeye de ekleyebilirsiniz. Bir tek başına .rc dosyasını (projenin dışında bir tane) oluşturulamıyor. [Kaynak şablonları](../windows/how-to-use-resource-templates.md) (.rct dosyaları) dilediğiniz zaman oluşturulabilir.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Kaynak dosyaları](../windows/resource-files-visual-studio.md)  
[Kaynak Düzenleyicileri](../windows/resource-editors.md)