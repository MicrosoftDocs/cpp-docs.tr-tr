---
description: 'Daha fazla bilgi edinin: proje dosyaları'
title: Örnek proje dosyası
ms.date: 08/19/2019
helpviewer_keywords:
- .vcxproj files
- C++ projects, project file format
ms.assetid: 5261cf45-3136-40a6-899e-dc1339551401
ms.openlocfilehash: caadd7c88b910b522868a6481219a3169cab2593
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225771"
---
# <a name="project-files"></a>Proje Dosyaları

Visual Studio 'daki bir C++ proje dosyası,. vcxproj dosya adı uzantısına sahip XML tabanlı bir dosyadır ve bir C++ projesi oluşturmak için gereken bilgileri içerir. Proje dosyasının ". props" veya ". targets" uzantısına sahip çeşitli proje dosyalarını içe aktardığına unutmayın. Bu dosyalar ek derleme bilgileri içerir ve bunların kendisi diğer ". props" veya ". targets" dosyalarına başvurabilir. Dosya yolundaki makrolar (örneğin `$(VCTargetsPath)` ), Visual Studio yüklemenize bağımlıdır. Bu makrolar ve ". props" ve ". targets" dosyaları hakkında daha fazla bilgi için bkz. [VC + + dizinleri Özellik sayfası](vcpp-directories-property-page.md), [Visual Studio 'da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md) ve [derleme komutları ve özellikleri için ortak makrolar](common-macros-for-build-commands-and-properties.md).

## <a name="example"></a>Örnek

::: moniker range=">=msvc-160"

Aşağıdaki Sample. vcxproj dosyası **Yeni proje** Iletişim kutusunda **Windows Masaüstü Sihirbazı** ' nı seçerek üretildi. Bir proje dosyasını işlemek için komut satırında msbuild.exe aracını veya IDE 'deki **Build** komutunu kullanın. (Gerekli kaynak ve üst bilgi dosyaları sağlanmadığından Bu örnek işlenemiyor.) Proje dosyasındaki XML öğeleri hakkında daha fazla bilgi için bkz. [Proje dosya şeması başvurusu](/visualstudio/msbuild/msbuild-project-file-schema-reference).

::: moniker-end

::: moniker range="<=msvc-150"

Aşağıdaki Sample. vcxproj dosyası **Yeni proje** iletişim kutusunda bir **Win32 konsol uygulaması** belirtilerek üretildi. Bir proje dosyasını işlemek için komut satırında msbuild.exe aracını veya IDE 'deki **Build** komutunu kullanın. (Gerekli kaynak ve üst bilgi dosyaları sağlanmadığından Bu örnek işlenemiyor.) Proje dosyasındaki XML öğeleri hakkında daha fazla bilgi için bkz. [Proje dosya şeması başvurusu](/visualstudio/msbuild/msbuild-project-file-schema-reference).

::: moniker-end

>[!NOTE]
> Visual Studio 2017 ve önceki sürümlerde bulunan projeler için `pch.h` ve olarak `stdafx.h` değiştirin `pch.cpp` `stdafx.cpp` .

```xml
<?xml version="1.0" encoding="utf-8"?>
<Project DefaultTargets="Build" ToolsVersion="4.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <ItemGroup Label="ProjectConfigurations">
    <ProjectConfiguration Include="Debug|Win32">
      <Configuration>Debug</Configuration>
      <Platform>Win32</Platform>
    </ProjectConfiguration>
    <ProjectConfiguration Include="Release|Win32">
      <Configuration>Release</Configuration>
      <Platform>Win32</Platform>
    </ProjectConfiguration>
  </ItemGroup>
  <PropertyGroup Label="Globals">
    <ProjectGuid>{96F21549-A7BF-4695-A1B1-B43625B91A14}</ProjectGuid>
    <Keyword>Win32Proj</Keyword>
    <RootNamespace>SomeProjName</RootNamespace>
  </PropertyGroup>
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.Default.props" />
  <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'" Label="Configuration">
    <ConfigurationType>Application</ConfigurationType>
    <CharacterSet>Unicode</CharacterSet>
  </PropertyGroup>
  <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|Win32'" Label="Configuration">
    <ConfigurationType>Application</ConfigurationType>
    <WholeProgramOptimization>true</WholeProgramOptimization>
    <CharacterSet>Unicode</CharacterSet>
  </PropertyGroup>
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />
  <ImportGroup Label="ExtensionSettings">
  </ImportGroup>
  <ImportGroup Label="PropertySheets" Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'">
    <Import Project="$(UserRootDir)\Microsoft.Cpp.$(Platform).user.props" Condition="exists('$(UserRootDir)\Microsoft.Cpp.$(Platform).user.props')" Label="LocalAppDataPlatform" />
  </ImportGroup>
  <ImportGroup Label="PropertySheets" Condition="'$(Configuration)|$(Platform)'=='Release|Win32'">
    <Import Project="$(UserRootDir)\Microsoft.Cpp.$(Platform).user.props" Condition="exists('$(UserRootDir)\Microsoft.Cpp.$(Platform).user.props')" Label="LocalAppDataPlatform" />
  </ImportGroup>
  <PropertyGroup Label="UserMacros" />
  <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'">
    <LinkIncremental>true</LinkIncremental>
  </PropertyGroup>
  <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|Win32'">
    <LinkIncremental>false</LinkIncremental>
  </PropertyGroup>
  <ItemDefinitionGroup Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'">
    <ClCompile>
      <PrecompiledHeader>Use</PrecompiledHeader>
      <WarningLevel>Level3</WarningLevel>
      <MinimalRebuild>true</MinimalRebuild>
      <DebugInformationFormat>EditAndContinue</DebugInformationFormat>
      <Optimization>Disabled</Optimization>
      <BasicRuntimeChecks>EnableFastChecks</BasicRuntimeChecks>
      <RuntimeLibrary>MultiThreadedDebugDLL</RuntimeLibrary>
      <PreprocessorDefinitions>WIN32;_DEBUG;_CONSOLE;%(PreprocessorDefinitions)</PreprocessorDefinitions>
    </ClCompile>
    <Link>
      <SubSystem>Console</SubSystem>
      <GenerateDebugInformation>true</GenerateDebugInformation>
    </Link>
  </ItemDefinitionGroup>
  <ItemDefinitionGroup Condition="'$(Configuration)|$(Platform)'=='Release|Win32'">
    <ClCompile>
      <WarningLevel>Level3</WarningLevel>
      <PrecompiledHeader>Use</PrecompiledHeader>
      <DebugInformationFormat>ProgramDatabase</DebugInformationFormat>
      <Optimization>MaxSpeed</Optimization>
      <RuntimeLibrary>MultiThreadedDLL</RuntimeLibrary>
      <FunctionLevelLinking>true</FunctionLevelLinking>
      <IntrinsicFunctions>true</IntrinsicFunctions>
      <PreprocessorDefinitions>WIN32;NDEBUG;_CONSOLE;%(PreprocessorDefinitions)</PreprocessorDefinitions>
    </ClCompile>
    <Link>
      <SubSystem>Console</SubSystem>
      <GenerateDebugInformation>true</GenerateDebugInformation>
      <EnableCOMDATFolding>true</EnableCOMDATFolding>
      <OptimizeReferences>true</OptimizeReferences>
    </Link>
  </ItemDefinitionGroup>
  <ItemGroup>
    <None Include="ReadMe.txt" />
  </ItemGroup>
  <ItemGroup>
    <ClInclude Include="pch.h" />
    <ClInclude Include="targetver.h" />
  </ItemGroup>
  <ItemGroup>
    <ClCompile Include="SomeProjName.cpp" />
    <ClCompile Include="pch.cpp">
      <PrecompiledHeader Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'">Create</PrecompiledHeader>
      <PrecompiledHeader Condition="'$(Configuration)|$(Platform)'=='Release|Win32'">Create</PrecompiledHeader>
    </ClCompile>
  </ItemGroup>
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.targets" />
  <ImportGroup Label="ExtensionTargets">
  </ImportGroup>
</Project>
```

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio projeleri-C++](../creating-and-managing-visual-cpp-projects.md)<br>
[Visual Studio’da C++ derleyicisi ve derleme özelliklerini ayarlama](../working-with-project-properties.md)
