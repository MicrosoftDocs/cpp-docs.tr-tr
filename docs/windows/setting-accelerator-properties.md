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
ms.openlocfilehash: b89f409fcf5a856a2207dd8efa655728f57b3fe8
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43680141"
---
# <a name="setting-accelerator-properties"></a>Hızlandırıcı Özelliklerini Ayarlama

Hızlandırıcı özelliklerini ayarlayabileceğiniz [Özellikler penceresi](/visualstudio/ide/reference/properties-window) dilediğiniz zaman. Ayrıca **hızlandırıcı** Hızlandırıcı tablosunda Hızlandırıcı özelliklerini değiştirmek için düzenleyici. Kullanılarak yapılan değişiklikleri **özellikleri** penceresi veya **hızlandırıcı** Düzenleyicisi sahip aynı sonucu: düzenlemeleri Hızlandırıcı tablosunda anında yansıtılır.

Her Hızlandırıcı kimliği için üç özellik vardır:

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