# Accellence CycloneDX Property Taxonomy, v1.0.0

This is the official Accellence property taxonomy for CycloneDX.

It documents all custom key/value <code>properties</code> that may be added in CycloneDX SBOMs created for software products & components provided by Accellence Technologies GmbH (Hannover, Germany).

For more information about CycloneDX property taxonomies, refer to
their [official documentation](https://github.com/CycloneDX/cyclonedx-property-taxonomy).


## <code>accellence</code> Namespace Taxonomy

<table>
<thead>
    <tr>
        <th>Namespace</th>
        <th>Description</th>
    </tr>
</thead>
<tbody>
    <tr style="vertical-align: top;">
        <td><b><code>accellence:about</code></b></td>
        <td>Namespace for any Accellence specific properties used for visualization in the application about dialogs.</td>
    </tr>
    <tr style="vertical-align: top;">
        <td><b><code>accellence:artifact</code></b></td>
        <td>Namespace for all Accellence specific properties associated the artifacts.</td>
    </tr>
    <tr style="vertical-align: top;">
        <td><b><code>accellence:metadata</code></b></td>
        <td>Namespace for all Accellence specific properties regarding any metadata (like license information, etc.).</td>
    </tr>
    <tr style="vertical-align: top;">
        <td><b><code>accellence:metadata:legal</code></b></td>
        <td>Namespace for all Accellence specific properties regarding any legal advisaries.</td>
    </tr>
    <tr style="vertical-align: top;">
        <td><b><code>accellence:signature</code></b></td>
        <td>Namespace for any Accellence specific properties regarding signatures.</td>
    </tr>
    <tr style="vertical-align: top;">
        <td><b><code>accellence:vulnerability</code></b></td>
        <td>Namespace for any Accellence specific properties regarding vulnerabilities.</td>
    </tr>
</tbody>
</table>


## <code>accellence:about</code> Namespace Taxonomy

<table>
<thead>
    <tr>
        <th>Property</th>
        <th>Description</th>
        <th>Type</th>
        <th>Property of</th>
    </tr>
</thead>
<tbody>
    <tr style="vertical-align: top;">
        <td><b><code>accellence:about:icon</code></b></td>
        <td>Image prominently displayed in the list appearance of a component or service in the application about dialogs.</td>
        <td>data:image;base64</td>
        <td><code>component/properties</code><br /><code>service/properties</td>
    </tr>
    <tr style="vertical-align: top;">
        <td><b><code>accellence:about:publish</code></b></td>
        <td>A flag indicating whether the component or service appears in the application about dialogs (<code>true</code>) or not (<code>false</code>).</td>
        <td>bool</td>
        <td><code>component/properties</code><br /><code>service/properties</td>
    </tr>
    <tr style="vertical-align: top;">
        <td><b><code>accellence:about:sortKey</code></b></td>
        <td>Integer value defines the order of appearance of a component or service in the application about dialogs.</td>
        <td>integer</td>
        <td><code>component/properties</code><br /><code>service/properties</td>
    </tr>
    <tr style="vertical-align: top;">
        <td><b><code>accellence:about:urls.homepage</code></b></td>
        <td>URL to the homepage of the components issuer/project.</td>
        <td>URL</td>
        <td><code>component/properties</code><br /><code>service/properties</td>
    </tr>
    <tr style="vertical-align: top;">
        <td><b><code>accellence:about:urls.download</code></b></td>
        <td>Download URL to obtain the of the component packages or sourcecode.</td>
        <td>URL</td>
        <td><code>component/properties</code><br /><code>service/properties</td>
    </tr>
</tbody>
</table>


## <code>accellence:artifact</code> Namespace Taxonomy

<table>
<thead>
    <tr>
        <th>Property</th>
        <th>Description</th>
        <th>Type</th>
        <th>Property of</th>
    </tr>
</thead>
<tbody>
    <tr style="vertical-align: top;">
        <td><b><code>accellence:artifact:files</code></b></td>
        <td>Array of file describers of the artifacts content.
        <br /><code>"(hash:[HASH]|fileName:[NAME]|modifiable:[0/1]|optional:[0/1]),..."</code></td>
        <td>objectlist</td>
        <td><code>component/properties</code><br /><code>service/properties</td>
    </tr>
    <tr style="vertical-align: top;">
        <td><b><code>accellence:artifact:linkage</code></b></td>
        <td>Only mandatory if the license is a weak or strong copyleft license (e.g., GPL, LGPL).<br><br>
            Specifies how the component was integrated in the software.<br><br>
    		<ul>
    		  <li><strong>dynamic</strong> = The component and other components of the software are compiled separately. The generated objects are kept separately (i.e., in separate directories). The component is linked at runtime to form a joint object code. In case of Java, the component is integrated via the import mechanism in Java (i.e. classloader).</li>
    		  <li><strong>static</strong> = The component and other components of the software are compiled separately, and the generated objects are linked during an offline process to create a single software component to be distributed.</li>
    		  <li><strong>snippet</strong> = A part of the source code of the component is added to the source code of the software.</li>
    		  <li><strong>seperated</strong> = There is no connection between the component and the software at all. The component is distributed along with the software. The only connection to the component is the call to an executable. The components communicate via the inter-process communication mechanisms only (e.g., via file, signal, socket, message queue, pipe, named pipe, semaphore, shared memory, memory mapped files). A further investigation would be needed for message passing. The component is kept separately from the software (i.e., in separate directories).</li>
    		</ul>
		</td>
        <td>enum: [dynamic, static, snippet, seperated]</td>
        <td><code>component/properties</code><br /><code>service/properties</td>
    </tr>
    <tr style="vertical-align: top;">
        <td><b><code>accellence:artifact:primaryLanguage</code></b></td>
        <td>Indicates the primary programming language the artifact is written in.</td>
        <td>string</td>
        <td><code>component/properties</code><br /><code>service/properties</td>
    </tr>
</tbody>
</table>


## <code>accellence:metadata</code> Namespace Taxonomy

<table>
<thead>
    <tr>
        <th>Property</th>
        <th>Description</th>
        <th>Type</th>
        <th>Property of</th>
    </tr>
</thead>
<tbody>
    <tr style="vertical-align: top;">
        <td><b><code>accellence:metadata:direct</code></b></td>
        <td>A flag indicating whether the component is a direct dependency (<code>true</code>)<br />or a transitive dependency (<code>false</code>).</td>
        <td>bool</td>
        <td><code>component/properties</code><br /><code>service/properties</td>
    </tr>
</tbody>
</table>


## <code>accellence:metadata:legal</code> Namespace Taxonomy

<table>
<thead>
    <tr>
        <th>Property</th>
        <th>Description</th>
        <th>Type</th>
        <th>Property of</th>
    </tr>
</thead>
<tbody>
    <tr style="vertical-align: top;">
        <td><b><code>accellence:metadata:legal:licenseObligations</code></b></td>
        <td>Important information to fulfill the license obligations for a distribution.</td>
        <td>string</td>
        <td><code>component/properties</code><br /><code>service/properties</td>
    </tr>
    <tr style="vertical-align: top;">
        <td><b><code>accellence:metadata:legal:additionalCopyrightInformation</code></b></td>
        <td>The content of additional copyright information (e.g. NOTICE file - Apache License or additional hints in the license text, readme or authors, contributors files).</td>
        <td>string</td>
        <td><code>component/properties</code><br /><code>service/properties</td>
    </tr>
    <tr style="vertical-align: top;">
        <td><b><code>accellence:metadata:legal:thirdPartyNotices</code></b></td>
        <td>The contents of all third-party notices found for the component, if any. Note that this is <i>not</i> the
            path to the notice files, but the actual notice text (which may be quite a lot of text). Third-party
            notices are provided by the component's author.<br>
            Since CycloneDX allows only a single String value for this, we separate different notice files by two
            consecutive line feeds.</td>
        <td>string</td>
        <td><code>component/properties</code><br /><code>service/properties</td>
    </tr>
</tbody>
</table>


## <code>accellence:signature</code> Namespace Taxonomy

<table>
<thead>
    <tr>
        <th>Property</th>
        <th>Description</th>
        <th>Type</th>
        <th>Property of</th>
    </tr>
</thead>
<tbody>
    <tr style="vertical-align: top;">
        <td><b><code>accellence:signature:issuer:id</code></b></td>
        <td>Id of the issuer for sigining process.</code></td>
        <td>string</td>
        <td><code>component/properties</code><br /><code>service/properties</td>
    </tr>
    <tr style="vertical-align: top;">
        <td><b><code>accellence:signature:issuer:pipeline</code></b></td>
        <td>Information about the signing pipeline.</code></td>
        <td>string</td>
        <td><code>component/properties</code><br /><code>service/properties</td>
    </tr>
</tbody>
</table>


## <code>accellence:vulnerability</code> Namespace Taxonomy

<table>
<thead>
    <tr>
        <th>Property</th>
        <th>Description</th>
        <th>Type</th>
        <th>Property of</th>
    </tr>
</thead>
<tbody>
    <tr style="vertical-align: top;">
        <td><b><code>accellence:vulnerability:toolchain:id</code></b></td>
        <td>A unique identifier in the vulnerability handling toolchain, aside from referenced id's (like CVE).</td>
        <td>uuid</td>
        <td><code>vulnerability/properties</code></td>
    </tr>
    <tr style="vertical-align: top;">
        <td><b><code>accellence:vulnerability:toolchain:processed</code></b></td>
        <td>The date and time (timestamp) when the vulnerability record was first processed by the toolchain.</td>
        <td>date-time</td>
        <td><code>vulnerability/properties</code></td>
    </tr>
    <tr style="vertical-align: top;">
        <td><b><code>accellence:vulnerability:tracking:accits</code></b></td>
        <td>List of tracking ids regarding the vulnerability, e.g. for analysis or from helpdesk.</td>
        <td>list (comma seperated)</td>
        <td><code>vulnerability/properties</code></td>
    </tr>
    <tr style="vertical-align: top;">
        <td><b><code>accellence:vulnerability:tracking:fixed</code></b></td>
        <td>Information about product version containing a fix.</td>
        <td>string</td>
        <td><code>vulnerability/properties</code></td>
    </tr>
</tbody>
</table>


## Contributing

These properties are maintained by Accellence Technologies.
Feel free to raise an issue if you have any questions.


## License

Copyright 2024 Accellence Technologies GmbH (Hannover, Germany).

Licensed under [Apache License 2.0](./LICENSE).
