---
title: Hızlandırıcı özelliklerini ayarlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- accelerator properties
- properties [C++], accelerator properties
- Type property
- Key property
- Modifier property
ms.assetid: 0fce9156-3025-4e18-b034-e219a4c65812
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5d47dffb782da1094c157a7bbd21c40ab6ba9fef
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42606710"
---
# <a name="setting-accelerator-properties"></a>Hızlandırıcı Özelliklerini Ayarlama

Hızlandırıcı özelliklerini ayarlayabileceğiniz [Özellikler penceresi](/visualstudio/ide/reference/properties-window) dilediğiniz zaman. Ayrıca **hızlandırıcı** Hızlandırıcı tablosunda Hızlandırıcı özelliklerini değiştirmek için düzenleyici. Kullanılarak yapılan değişiklikleri **özellikleri** penceresi veya **hızlandırıcı** Düzenleyicisi sahip aynı sonucu: düzenlemeleri Hızlandırıcı tablosunda anında yansıtılır.

Her hızlandırıcının için üç özellik [kimliği](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/3487f185-de96-4b1d-87db-034a52223160):

- [Değiştirme özelliği](../windows/accelerator-modifier-property.md) denetimi için kısayol tuş birleşimleri ayarlar.

   > [!NOTE]
   > İçinde **özellikleri** penceresi, bu özellik görünür üç ayrı Boolean özelliği, her biri denetlenebilir bağımsız olarak: **Alt**, **Ctrl**ve **Shift**.

- [Anahtar özellik](../windows/accelerator-key-property.md) Hızlandırıcı olarak kullanılacak gerçek anahtarı ayarlar.

- [Türü özelliği](../windows/accelerator-type-property.md) anahtarı sanal (VIRTKEY'e) veya ASCII/ANSI olarak yorumlanır olup olmadığını belirler.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Önceden Tanımlanmış Hızlandırıcı Tuşları](../windows/predefined-accelerator-keys.md)  
[Kaynak Düzenleyicileri](../windows/resource-editors.md)  
[Hızlandırıcı Düzenleyicisi](../windows/accelerator-editor.md)