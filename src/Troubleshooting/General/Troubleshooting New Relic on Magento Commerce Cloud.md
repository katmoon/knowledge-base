---
title: Troubleshooting New Relic on Magento Commerce Cloud
link: https://support.magento.com/hc/en-us/articles/360041937912-Troubleshooting-New-Relic-on-Magento-Commerce-Cloud
labels: Magento Commerce Cloud,PHP,New Relic,GraphQL,New Relic problem,New Relic troubleshooting,accessing New Relic,how to,troubleshoot,display
---

<p>This article provides resources for troubleshooting New Relic on Magento Commerce Cloud.</p>
<table>
<tbody>
<tr>
<td>Issue </td>
<td>Cause</td>
<td>Resources</td>
</tr>
<tr>
<td>Access Issues</td>
</tr>
<tr>
<td>
<p>Can't see projects in New Relic.</p>
<p>You log in to New Relic but can't see projects you should be entitled to view/access. </p>
</td>
<td>
<p>In those cases, an admin user needs to add you to the project.</p>
</td>
<td>
<p>Support Help Center <a href="https://support.magento.com/hc/en-us/articles/360039127712">Accessing New Relic services</a> article.</p>
</td>
</tr>
<tr>
<td>Data Issues</td>
</tr>
<tr>
<td>
<p>Missing data after installation.</p>
<p>Use the <a href="https://docs.newrelic.com/docs/agents/manage-apm-agents/troubleshooting/new-relic-diagnostics">New Relic Diagnostics utility</a> to try to identify the cause. If this does not help, look at agent specific solutions. Links to articles containing these solutions are in the right-hand column.</p>
</td>
<td>
<p>Missing data can have different causes. You may need to:</p>
<ul>
<li>Verify the agent is installed.</li>
<li>Verify your app name and license key.</li>
<li>Restart your web server.</li>
<li>Make sure your system meets compatibility requirements.</li>
<li>INI settings.</li>
</ul>
</td>
<td>
<ul>
<li><a href="https://docs.newrelic.com/docs/agents/manage-apm-agents/troubleshooting/not-seeing-data#apm-agents">New Relic Documentation &gt; APM Agents &gt; Not Seeing Data</a></li>
<li><a href="https://docs.newrelic.com/docs/agents/manage-apm-agents/troubleshooting/not-seeing-data#browser-agent">New Relic Documentation &gt; New Relic Browser &gt; Not Seeing Data</a></li>
<li><a href="https://docs.newrelic.com/docs/agents/manage-apm-agents/troubleshooting/not-seeing-data#infrastructure-agents">New Relic Documentation &gt; New Relic Infrastructure &gt; Not Seeing Data</a></li>
<li><a href="https://docs.newrelic.com/docs/agents/manage-apm-agents/troubleshooting/not-seeing-data#mobile-agents">New Relic Documentation &gt; New Relic Mobile &gt; Not Seeing Data</a></li>
</ul>
</td>
</tr>
<tr>
<td>
<p>Transactions timestamp discrepancy.<br/><br/>You may struggle to find long transactions (more than 5 mins) using the New Relic UI. You may also find transactions displayed outside of the expected time frame. </p>
</td>
<td>
<p>The New Relic UI displays the time of the transaction's end, not the time when the transaction began. </p>
</td>
<td>
<p>To calculate the beginning of the transaction using the New Relic UI, check the duration of the transaction. Subtract the duration amount from the timestamp (end of transaction) provided by the New Relic UI. </p>
</td>
</tr>
<tr>
<td>
<p> NerdGraph GraphQL <code>curl</code> queries using special characters such as <code>|</code> and <code>%</code> do not work.</p>
</td>
<td>
<p>New Relic "copy to curl" feature within NerdGraph does not currently provide a way to handle special characters such as<code>|</code>and <code>%</code>.</p>
</td>
<td>
<p>Use a different API library to solve the issue with special characters. For example, GraphQLClient Library for Graphql API on Python, or Apache.commons by Java Language calls. Review client libraries on <a href="https://graphql.org/code/">GraphQL</a>.</p>
</td>
</tr>
<tr>
<td>
<p>Chart and dashboard display issues. </p>
</td>
<td>
<p>Resolve missing charts by adding New Relic domains to the allow list or uninstall the browser extension causing the issues. </p>
</td>
<td>
<p><a href="https://docs.newrelic.com/docs/apm/new-relic-apm/troubleshooting/charts-missing-or-do-not-render">New Relic Documentation &gt; Charts missing or do not render</a> </p>
</td>
</tr>
<tr>
<td>PHP Agent Issues</td>
</tr>
<tr>
<td>
<p>PHP agent does not show the correct instance count.</p>
</td>
<td>
<p>The number of instances can increase depending on back end processes and throughput. Differences between server values can be due to processes running on one server, but not the other server. </p>
</td>
<td>
<p><a href="https://docs.newrelic.com/docs/agents/php-agent/troubleshooting/troubleshoot-php-agent-instance-count">New Relic Documentation &gt; Troubleshoot the PHP agent instance count</a><br/>  </p>
</td>
</tr>
</tbody>
</table>