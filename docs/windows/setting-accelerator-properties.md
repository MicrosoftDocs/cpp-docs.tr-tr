---
title: Hızlandırıcı özelliklerini ayarlama (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- accelerator properties
- properties [C++], accelerator properties
- Type property
- Key property
- Modifier property
ms.assetid: 0fce9156-3025-4e18-b034-e219a4c65812
ms.openlocfilehash: 47ebd54fdaff099e3a8ce828581a66b0ec871915
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50647024"
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

[Önceden Tanımlanmış Hızlandırıcı Tuşları](../windows/predefined-accelerator-keys.md)<br/>
[Kaynak Düzenleyicileri](../windows/resource-editors.md)<br/>
[Hızlandırıcı Düzenleyicisi](../windows/accelerator-editor.md)