---
description: 'Daha fazla bilgi edinin: kaynak derleyicisi önemli hatası RC1052'
title: Kaynak Derleyicisi Önemli Hatası RC1052
ms.date: 11/04/2016
f1_keywords:
- RC1052
helpviewer_keywords:
- RC1052
ms.assetid: 59803673-492b-44fa-80fa-df93b8aaf9fb
ms.openlocfilehash: 41ef30cfde7d463337b1747b3f6141866e39e3be
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97255086"
---
# <a name="resource-compiler-fatal-error-rc1052"></a>Kaynak Derleyicisi Önemli Hatası RC1052

Derleyici sınırı: çok derin iç içe #if veya #ifdef blokları

Program, ve yönergeleri için izin verilen en yüksek iç içe geçme düzeylerini aştı `#if` `#ifdef` .

Bu hata, bu önişlemci yönergelerini kullanan içerme dosyalarından kaynaklanıyor olabilir.

Bu sorunu onarmak için kaynak dosyanızdaki iç içe geçmiş `#if` ve yönergeler sayısını azaltın `#ifdef` . Sorun, kaynak dosyanıza dahil olan üstbilgi dosyalarından kaynaklanıyorsa, üstbilgi dosyalarındaki iç içe geçmiş `#if` ve yönergeler sayısını azaltın `#ifdef` . Bu mümkün değilse, mevcut eklenen üst bilgi dosyalarında Önişlemci 'yi çalıştırarak kaynak dosyanızda yeni bir üst bilgi dosyası oluşturmayı ve eklemeyi düşünün. Daha fazla bilgi için bkz. [/p (bir dosyaya ön işleme)](../../build/reference/p-preprocess-to-a-file.md) derleyici seçeneği.
